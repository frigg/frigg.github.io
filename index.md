---
layout: docs
title: Documentation
---

## Configuration file
Frigg works without setup for some projects. However, you might want to have a
more specific configuration. We support configuration through a yaml file. If
you put `.frigg.yml` in the base of your repository frigg will read it and use
those settings while testing and building your project.

### Options

#### `tasks`
Should be defined as a list of commands. Those commands will be run in the
order they are defined during the run.

#### `webhooks` - optional
Should be defined as a list of urls where frigg can post status about the
build.

#### `services` - optional
Should be defined as a list of services where frigg can start before building and testing.
Examples of services are: redis-server or postgresql

#### `coverage` - optional
This option activates coverage reporting for the project. It needs two subparameter `path` and `parser`. The `path` option is the path to the coverage report file and the `parser` is the type of parser needed to parse the report file. Currentlyt available parsers: clover, cobertura and python. More information can be found in the [coverage reporting documentation](/coverage-reporting/).

### Example
{% highlight yaml %}
tasks:
 - tox
 - flake8
 - coverage xml

services:
 - postgresql

coverage:
  path: coverage.xml
  parser: python
{% endhighlight %}

## Badges

### Build badge [![Example badge for frigg/frigg](https://ci.frigg.io/badges/frigg/frigg/)](https://ci.frigg.io/frigg/frigg/last/)

To get a nice build badge in your readme to show everyone that you build is a success, or warn people that it is broken and the master branch might not work at the moment, just add the code below.

#### Markdown
```
[![Build status](https://ci.frigg.io/badges/<owner>/<repo>/)](https://ci.frigg.io/<owner>/<repo>/last/)
```

#### reStructuredText
```
.. image:: https://ci.frigg.io/badges/<owner>/<repo>/
     :target: https://ci.frigg.io/<owner>/<repo>/last/
     :alt: Build Status
```

#### RDoc
```
{<img src="https://ci.frigg.io/badges/<owner>/<repo>/" alt="Build Status" />}[https://ci.frigg.io/<owner>/<repo>/last/]
```

#### HTML
```
<a href="https://ci.frigg.io/<owner>/<repo>/last/"><img src="https://ci.frigg.io/badges/<owner>/<repo>/" alt="Build Status" /></a>
```

### Coverage badge [![Example badge for frigg/frigg](https://ci.frigg.io/badges/coverage/frigg/frigg/)](https://ci.frigg.io/frigg/frigg/last/)

To get a nice build badge in your readme to show everyone that you build is a success, or warn people that it is broken and the master branch might not work at the moment, just add the code below.

#### Markdown
```
[![Build status](https://ci.frigg.io/badges/coverage/<owner>/<repo>/)](https://ci.frigg.io/<owner>/<repo>/last/)
```

#### reStructuredText
```
.. image:: https://ci.frigg.io/badges/coverage/<owner>/<repo>/
     :target: https://ci.frigg.io/<owner>/<repo>/last/
     :alt: Build Status
```

#### RDoc
```
{<img src="https://ci.frigg.io/badges/coverage/<owner>/<repo>/" alt="Build Status" />}[https://ci.frigg.io/<owner>/<repo>/last/]
```

#### HTML
```
<a href="https://ci.frigg.io/coverage/<owner>/<repo>/last/"><img src="https://ci.frigg.io/badges/<owner>/<repo>/" alt="Build Status" /></a>
```

## Approval
Since frigg is in a beta phase all projects need approval before they can be
built on. If you think it is taking way to long before your project is
approved you can send us a mail at hi@frigg.io.

## About Github permissions
We ask for write permissions to your repositories. We actually do not want to,
however there is no way around this. Github does not have a permission scope in
their API that gives read-only access to repositories. We try our best to keep
the scope of the permissions we ask for at a minimum.
