[<img src="https://sling.apache.org/res/logos/sling.png"/>](https://sling.apache.org)

 [![Build Status](https://ci-builds.apache.org/job/Sling/job/modules/job/sling-org-apache-sling-contentparser-api/job/master/badge/icon)](https://ci-builds.apache.org/job/Sling/job/modules/job/sling-org-apache-sling-contentparser-api/job/master/) [![Test Status](https://img.shields.io/jenkins/tests.svg?jobUrl=https://ci-builds.apache.org/job/Sling/job/modules/job/sling-org-apache-sling-contentparser-api/job/master/)](https://ci-builds.apache.org/job/Sling/job/modules/job/sling-org-apache-sling-contentparser-api/job/master/test/?width=800&height=600) [![Coverage](https://sonarcloud.io/api/project_badges/measure?project=apache_sling-org-apache-sling-contentparser-api&metric=coverage)](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-contentparser-api) [![Sonarcloud Status](https://sonarcloud.io/api/project_badges/measure?project=apache_sling-org-apache-sling-contentparser-api&metric=alert_status)](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-contentparser-api) [![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.apache.sling/org.apache.sling.contentparser.api/badge.svg)](https://search.maven.org/#search%7Cga%7C1%7Cg%3A%22org.apache.sling%22%20a%3A%22org.apache.sling.contentparser.api%22) [![JavaDocs](https://www.javadoc.io/badge/org.apache.sling/org.apache.sling.contentparser.api.svg)](https://www.javadoc.io/doc/org.apache.sling/org.apache.sling.contentparser.api) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) [![contentparser](https://sling.apache.org/badges/group-contentparser.svg)](https://github.com/apache/sling-aggregator/blob/master/docs/groups/contentparser.md)

Apache Sling Content Parser API
====
This module is part of the [Apache Sling](https://sling.apache.org) project.

The Apache Sling Content Parser API provides support for parsing various files capable of abstracting a Sling resource tree. This API is a 
continuation of the one provided by the [Apache Sling JCR Content Parser](https://github.com/apache/sling-org-apache-sling-jcr-contentparser) bundle. Although very similar, there are some notable changes:

1. the API is now available in the `org.apache.sling.contentparser.api` package;
2. there is no replacement for the `org.apache.sling.jcr.contentparser.ContentParserFactory`; to obtain a `ContentParser`, given that 
they are exposed as OSGi services, one has to filter on the `ContentParser.SERVICE_PROPERTY_CONTENT_TYPE` service registration property,
to select the appropriate file format;
3. as a consequence of 2., the `ParserOptions` are now passed directly to the `ContentParser#parse` method.

Implementations of the API are made available from separate bundles:
1. JSON - [`org.apache.sling.contentparser.json`](https://github.com/apache/sling-org-apache-sling-contentparser-json)
2. XML - [`org.apache.sling.contentparser.xml`](https://github.com/apache/sling-org-apache-sling-contentparser-xml)
3. Jackrabbit Filevault XML ([Enhanced JCR 2.0 Document View](https://jackrabbit.apache.org/filevault/docview.html)) - [`org.apache.sling.contentparser.xml-jcr`](https://github.com/apache/sling-org-apache-sling-contentparser-xml-jcr) (the only module depending on the JCR / 
Jackrabbit APIs)
