# aegis-platform-bom

Shared Maven **parent POM + dependency BOM** for every Aegis service. Pins Spring Boot 4.1.0,
Java 21, and common plugin config (surefire/failsafe, JaCoCo coverage gate, SpotBugs SAST, OWASP
Dependency-Check), plus dependency management for the shared libraries and security-relevant
third-party libs (Bouncy Castle, OpenSAML).

Every service declares `io.aegis:aegis-platform-parent:0.1.0` as its `<parent>`.

## Build
```bash
mvn install   # installs the parent POM to ~/.m2 (build this first)
```
