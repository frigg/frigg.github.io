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
