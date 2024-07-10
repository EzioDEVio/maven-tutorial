[![Java CI with Maven](https://github.com/EzioDEVio/maven-tutorial/actions/workflows/maven.yml/badge.svg)](https://github.com/EzioDEVio/maven-tutorial/actions/workflows/maven.yml)

# Maven Tutorial

## Introduction

This project is a simple Maven-based Java application. Maven is a powerful build automation and project management tool primarily used for Java projects. It uses a configuration file known as the Project Object Model (POM), which is stored in a `pom.xml` file. Maven helps manage project dependencies, build processes, and other project-related tasks.

## What is Maven?

Maven is a build automation tool used primarily for Java projects. It provides a uniform build system, project dependency management, and documentation management. Maven addresses two aspects of building software:

1. **How software is built**: By defining the build process and dependencies in a standardized way.
2. **Its dependencies**: By managing external libraries and frameworks that a project depends on.

### Key Features of Maven:
- **Standardized Build Process**: Defines a standard way to build projects, making the build process consistent across different projects.
- **Dependency Management**: Automatically downloads and manages libraries and plugins required for a project.
- **Project Information**: Maintains a detailed description of the project, including metadata like version, description, developers, and more.
- **Build Lifecycle**: Defines a lifecycle for building projects, which includes phases like validate, compile, test, package, verify, install, and deploy.

## The `pom.xml` File

The `pom.xml` file is the core of a Maven project. It defines the project structure, dependencies, build configuration, and other project information.

### Explanation of `pom.xml`

Here's a breakdown of the `pom.xml` file used in this project:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <groupId>com.example</groupId>
  <artifactId>my-maven-app</artifactId>
  <version>1.0-SNAPSHOT</version>

  <name>my-maven-app</name>
  <!-- FIXME change it to the project's website -->
  <url>http://www.example.com</url>

  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>11</maven.compiler.source>
    <maven.compiler.target>11</maven.compiler.target>
  </properties>

  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.11</version>
      <scope>test</scope>
    </dependency>
  </dependencies>

  <build>
    <plugins>
      <!-- clean lifecycle, see https://maven.apache.org/ref/current/maven-core/lifecycles.html#clean_Lifecycle -->
      <plugin>
        <artifactId>maven-clean-plugin</artifactId>
        <version>3.1.0</version>
      </plugin>
      <!-- default lifecycle, jar packaging: see https://maven.apache.org/ref/current/maven-core/default-bindings.html#Plugin_bindings_for_jar_packaging -->
      <plugin>
        <artifactId>maven-resources-plugin</artifactId>
        <version>3.0.2</version>
      </plugin>
      <plugin>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.8.0</version>
        <configuration>
          <source>${maven.compiler.source}</source>
          <target>${maven.compiler.target}</target>
        </configuration>
      </plugin>
      <plugin>
        <artifactId>maven-surefire-plugin</artifactId>
        <version>2.22.1</version>
      </plugin>
      <plugin>
        <artifactId>maven-jar-plugin</artifactId>
        <version>3.0.2</version>
      </plugin>
      <plugin>
        <artifactId>maven-install-plugin</artifactId>
        <version>2.5.2</version>
      </plugin>
      <plugin>
        <artifactId>maven-deploy-plugin</artifactId>
        <version>2.8.2</version>
      </plugin>
      <!-- site lifecycle, see https://maven.apache.org/ref/current/maven-core/lifecycles.html#site_Lifecycle -->
      <plugin>
        <artifactId>maven-site-plugin</artifactId>
        <version>3.7.1</version>
      </plugin>
      <plugin>
        <artifactId>maven-project-info-reports-plugin</artifactId>
        <
      <version>3.0.0</version>
    </plugin>
    <plugin>
      <groupId>org.codehaus.mojo</groupId>
      <artifactId>exec-maven-plugin</artifactId>
      <version>3.3.0</version>
      <configuration>
        <mainClass>com.example.App</mainClass>
      </configuration>
    </plugin>
  </plugins>
</build>
</project>
Explanation of Key Elements in pom.xml:
GroupId: A unique identifier for a project group. For example, com.example.
ArtifactId: A unique identifier for a specific project within a group. For example, my-maven-app.
Version: The version of the project. In this example, 1.0-SNAPSHOT indicates it's a development version.
Dependencies: External libraries required by the project. Here, JUnit is included as a dependency for testing purposes.
Build: Configuration of various Maven plugins used during the build process. Plugins include:
maven-clean-plugin: Cleans the project by deleting the target directory.
maven-resources-plugin: Copies project resources.
maven-compiler-plugin: Compiles the Java source code.
maven-surefire-plugin: Runs the unit tests.
maven-jar-plugin: Builds a JAR file of the project.
maven-install-plugin: Installs the built artifact into the local repository.
maven-deploy-plugin: Deploys the built artifact to a remote repository.
exec-maven-plugin: Executes the main class.

```
mvn exec:java -Dexec.mainClass=com.example.App
```

# License
This project is licensed under the MIT License - see the LICENSE file for details.
