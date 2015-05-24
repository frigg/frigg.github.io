---
layout: docs
title: Configuration
---

Frigg works without setup for some projects. However, you might want to have a
more specific configuration. We support configuration through a yaml file. If
you put `.frigg.yml` in the base of your repository Frigg will read it and use
those settings while testing and building your project.

## Options

#### `tasks`
Should be defined as a list of commands. Those commands will be run in the
order they are defined during the run.

#### `setup_tasks` - optional
This option can be used to install and setup the build environment. These tasks
will run before the regular tasks. The intention is to separate external installs
and dependencies from the code that the build should test. If they fail the build
will be marked as an error, while failed tasks is marked as failures. The result
of these tasks will be shown in its own section on Frigg

#### `coverage` - optional
This option activates coverage reporting for the project. It needs two
subparameter `path` and `parser`. The `path` option is the path to the
coverage report file and the `parser` is the type of parser needed to
parse the report file. Currently available parsers: clover, cobertura
and python. More information can be found in the
[coverage reporting documentation](/docs/coverage-reporting/).

#### `services` - optional
Should be defined as a list of services where Frigg can start before
building and testing. Examples of services are: redis-server or postgresql

#### `webhooks` - optional
Should be defined as a list of urls where Frigg can post status about the
build.


### Example
{% highlight yaml %}
setup_tasks:
 - apt-get install pandoc

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
