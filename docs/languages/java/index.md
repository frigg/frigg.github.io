---
layout: docs
title: Building java projects with frigg.io
---

Below you will find our view on best practices for using frigg.io
in your java projects.

## Java installation
The default java installation in the Frigg Container is Java 8. However, you may manually install
another java version by adding install steps in the setup step (ref setup step TODO).

## Build Using Maven
Maven can manage a project's build, reporting and documentation from a central piece of information.
Frigg is able to build and test maven projects from the pom.xml for the project,
for more specific information about pom.xml and configuration of maven
[See the maven docs](https://maven.apache.org/)

### -B option
Run in non-interactive (batch) mode

Batch mode is essential if you need to run Maven in a non-interactive, continuous integration environment.
When running in non-interactive mode, Maven will never stop to accept input from the user.
Instead, it will use sensible default values when it requires input.

For more command line options see [Maven Command Line Options](http://books.sonatype.com/mvnref-book/reference/running-sect-options.html)

#### Simple .frigg.yml
{% highlight yaml %}
tasks:
 - mvn -B test
{% endhighlight %}

## Coverage with Maven
Frigg also support reporting test coverage with Maven by using cobertura,
this will run mvn test and generate a coverage report which will be visualized on frigg.io.

For more information on coverage, see our documentation on [coverage reporting](/docs/coverage-reporting/).

#### .frigg.yml with coverage
{% highlight yaml %}
tasks:
 - mvn -B cobertura:cobertura

coverage:
  path: target/site/cobertura/coverage.xml
  parser: cobertura

{% endhighlight %}
