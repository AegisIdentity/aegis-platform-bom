# aegis-platform-bom — working notes

The Maven **parent POM** (`io.aegis:aegis-platform-parent`) all Aegis services inherit. Packaging
`pom`. Extends `spring-boot-starter-parent:4.1.0`.

## What lives here (and must stay consistent)
- Java release level: **21**. Spring Boot line: **4.1.0** (Spring Security 7.1, Spring AS 7.1).
- Plugin config: JaCoCo (coverage `check` bound to `verify`, floor via `${jacoco.line.coverage}`),
  surefire (`*Test`), failsafe (`*IT`), SpotBugs + OWASP Dependency-Check (pluginManagement; run in CI).
- `dependencyManagement` for `io.aegis:*` shared libs and Bouncy Castle / OpenSAML versions.

## Non-negotiables
- Re-verify the Boot/Security patch level before a release cut (new CVEs land continuously).
- Bump `aegis-commons.version` here when the commons libraries release; keep it the single source.

## Build
`mvn install`. Nothing to test (pom-only). Everything downstream depends on this being in `~/.m2`.
