# Play around with maven

When building your cicd pipeline you will need to build and start the application manually (i.e. without help of your IDE). We will practice this locally in this story.

## 1. Acceptance Criteria

Make sure that you can:
* Do a local build of your Spring Boot project using maven
* Run the output of the local build on the command-line

## 2. Implementation Details

Check the [reference material](<./../../../../reference/cicd/maven/1 - maven.md>) for some guidance on maven.

The output of your build should be a `.jar` file that can be ran on its own without any dependencies. If you followed the previous stories, the output of your project should produce such a jar file ([here](https://www.javadevjournal.com/spring-boot/spring-boot-standalone-application/) is an additional tutorial if necessary).

You can run a standalone jar file with `java -jar <jar-file>`.