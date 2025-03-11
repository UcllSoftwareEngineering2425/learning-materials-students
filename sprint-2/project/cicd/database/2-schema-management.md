# Schema Management

## 1. Acceptance Criteria

Currently every environment manages its database schema through a schema.sql file.

This should change to the following:

* The schema in the development environment is applied to H2 through Flyway
* The schema while running integration tests is applied to H2 through Flyway
* The schema in the production environment is applied to PostgreSQL through Flyway

The schema of production will thus be automatically updated when a new version reaches it.

## 2. Implementation Details

We will look at tools like "Flyway" to help us with versioning our database schema.

Check out the [resources on Flyway](./../../../reference/flyway/1%20-%20flyway.md) first so you have an idea what Flyway is about.

Flyway can be triggered from maven (during the build) or from Spring Boot (on application startup). We advise you to integrate Flyway in Spring Boot and not in Maven. To do so, perform the following steps:

* Add the necessary libraries to the pom.xml file
* Write the SQL for the existing schema in a first migration file
* Configure your production configuration so that Flyway executes your migration(s) in your Azure database on application start-up
* You no longer need your schema.sql file after configuring Flyway