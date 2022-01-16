---
title:  "AWS p2 Maven Plugin"
description: "Maven plugin for deploying a p2 update site to an AWS S3 bucket"
author: avojak
image: https://i.imgur.com/jBKy86C.png
tags:
  - Java
  - AWS
  - p2
  - Maven
---

A Maven plugin for deploying a p2 update site to an AWS S3 bucket.

For more details about the development of AWS p2 Maven Plugin, check out my blog post.

```xml
<plugin>
    <groupId>com.avojak.mojo</groupId>
    <artifactId>aws-p2-maven-plugin</artifactId>
    <version>2.0.0</version>
    <configuration>
        <bucket>p2.example.com</bucket>
    </configuration>
    <executions>
        <execution>
            <goals>
                <goal>deploy</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

GitHub Repository: [https://github.com/avojak/aws-p2-maven-plugin](https://github.com/avojak/aws-p2-maven-plugin)
Maven Central: [https://mvnrepository.com/artifact/com.avojak.mojo/aws-p2-maven-plugin](https://mvnrepository.com/artifact/com.avojak.mojo/aws-p2-maven-plugin)