---
paths:
  - "**/*.java"
---

# Java Environment Rules

- Use Maven/Gradle as Dependency management with spring boot BOM as version management
- When `Spring Boot` is used, try to exclude non-related `Spring Boot` dependencies if not applicable say for example, embedded tomcat

# Java Coding Rules

- Use logger instead of 'print' / 'println' statement
- Try make 'hardcode' value to be declare as constants rather just hardcode inline or even make it configurable
