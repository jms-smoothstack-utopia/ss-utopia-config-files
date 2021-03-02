# Utopia Configuration Files

This repository contains application properties that are shared and individual across all Utopia services. The repository is cloned and hosted by the [https://github.com/jms-smoothstack-utopia/ss-utopia-config-server](Utopia Config Server) and retrieved by the services through service discovery with Eureka.

These properties allow modifying and setting different profiles for runtime configuration for each server based on the need at the time.

`[application.properties](application.properties)` is a default configuration and is shared across all services. Others are activated per service name and profile name, where `application-local` would be the profile `local` in Spring Boot.

## Encrypted Properties
Encrypted properties (ie passwords) are stored in plaintext securely within these files. The configuration server will handle decryption at runtime before sending the values to the requesting server. Encrypted properties are stored in the form

```
key={cipher}<value>
```

### WARNING: The properties are decrypted in-flight so a secure tunnel must be used for transfer between the configuration server and the individual services.
