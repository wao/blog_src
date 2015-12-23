---
layout: post
title: Using androidannotation with M2E
tags: GT-I9502
---

Install ADT

Install m2e-android: Android for Maven Eclipse Update Site:	http://rgladwell.github.io/m2e-android/updates/	
It will also install m2e itself.

Install mvn-apt: Maven Integration for Eclipse JDT APT:	http://download.jboss.org/jbosstools/updates/m2e-extensions/m2e-apt

Create a maven android project. 

Add following dependencies:

	    <dependency>
        <groupId>org.androidannotations</groupId>
        <artifactId>androidannotations</artifactId>
        <version>3.2</version>
        <scope>provided</scope>
    </dependency>
    <dependency>
        <groupId>org.androidannotations</groupId>
        <artifactId>androidannotations-api</artifactId>
        <version>3.2</version>
    </dependency>	

And add following in build/pluginManager

         <plugin>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.1</version>
            <configuration>
                <source>1.6</source>
                <target>1.6</target>
            </configuration>
        </plugin>

Configure mvn-apt: Using delegated to mvn-processor-plugin. It is important, since default eclipse apt process is broken with m2e.

