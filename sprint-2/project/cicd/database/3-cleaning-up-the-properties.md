# Configuring the production environment

Currently some properties are baked into the backend JAR (like the allowed origins for CORS) and others are being generated automatically (JWT secret key, H2 password for dev). 

We would like to remove all hardcoded properties so we can also configure these properties in production.

## 1. Acceptance Criteria

At the end of this task the app should have no hard-coded properties anymore.

All properties should be configured in property-files.

All sensitive information (like passwords) should not be in git:
* Locally, use a "dev" profile configuration file that you do not check in
* On Azure, load sensitive properties via environment variables set in Azure

Your repository should contain **no** sensitive information.