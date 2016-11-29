# Atomist 'atomist-bom'

[![Build Status](https://travis-ci.org/atomist/atomist-bom.svg?branch=master)](https://travis-ci.org/atomist/atomist-bom) [![Slack Status](https://join.atomist.com/badge.svg)](https://join.atomist.com)

The Atomist BOM (Bill Of Materials) dependency keeps track of version
numbers and ensure that all dependencies (both direct and transitive)
are at the same version.

## Using

Maven provides a tag `dependencyManagement` for this purpose. You need
to add the bom information in this tag as follows:

```xml
<?xml version='1.0' encoding='UTF-8'?>
<project
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://maven.apache.org/POM/4.0.0">
    <modelVersion>4.0.0</modelVersion>
    ...
    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>com.atomist</groupId>
                <artifactId>atomist-bom</artifactId>
                <version>0.1.0</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>
```
