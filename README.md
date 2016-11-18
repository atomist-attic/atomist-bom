# Atomist 'atomist-bom'

![Build Status](https://travis-ci.com/atomist/atomist-bom.svg?token=z8gZcM8P34vnbufzQBTa&branch=master)

The Atomist BOM (Bill Of Materials) dependency keeps track of version numbers and ensure that all dependencies (both direct and transitive) are at the same version.

###How to add the atomist-bom dependency

Maven provides a tag `dependencyManagement` for this purpose. You need to add the bom information in this tag as follows: 
```
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