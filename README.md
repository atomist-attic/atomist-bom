# Atomist 'atomist-bom'

[![Build Status](https://travis-ci.org/atomist/atomist-bom.svg?branch=master)](https://travis-ci.org/atomist/atomist-bom)
[![Slack Status](https://join.atomist.com/badge.svg)](https://join.atomist.com)

The Atomist BOM (Bill Of Materials) dependency keeps track of version
numbers and ensure that all dependencies (both direct and transitive)
are at the same version.

## Use

Maven provides a tag `dependencyManagement` for this purpose. You can
add the bom information in this tag as follows:

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
                <version>0.6.0</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>
```

## Developing

You can build, test, and install the project locally with [maven][].

[maven]: https://maven.apache.org/

```sh
$ mvn install
```

To create a new release of the project, simply push a tag of the form
`M.N.P` where `M`, `N`, and `P` are integers that form the next
appropriate [semantic version][semver] for release.  For example:

```sh
$ git tag -a 1.2.3
```

The [Travis CI][travis] build will automatically create a GitHub
release using the tag name for the release and the comment provided on
the annotated tag as the contents of the release notes.  It will also
automatically upload the needed artifacts.

[semver]: http://semver.org
[travis]: https://travis-ci.org/atomist/atomist-bom
