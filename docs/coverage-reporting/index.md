---
layout: docs
title: Coverage reporting
---

## Settings in .frigg.yml
This option activates coverage reporting for the project. It needs two
subparameter `path` and `parser`. The `path` option is the path to the
coverage report file and the `parser` is the type of parser needed to
parse the report file.

{% highlight yaml %}
coverage:
  path: coverage.xml
  parser: python
{% endhighlight %}

## Parsers
* clover
* cobertura
* python

## Different types of coverage reporters

#### istanbul
```
istanbul report cobertura
```

#### coverage.py
```
coverage xml
```

#### maven-cobertura
```
mvn cobertura:cobertura
```
