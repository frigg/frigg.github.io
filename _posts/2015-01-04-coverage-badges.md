---
layout: post
author: relekang
title: Coverage badges
category: Features
slug: coverage-badges
---

We recently started to support coverage reporting and coverage badges. At this point we support clover and cobertura xml files. If your project uses a coverage tool that can export to one of these formats you can start using the badges right away. Below is an example badge from the [frigg/frigg-coverage](https://github.com/frigg/frigg-coverage) project that we use to parse the coverage files.

<div style="text-align:center; margin: 1em auto;">
<img src="http://ci.frigg.io/badges/coverage/frigg/frigg-coverage/" alt="Coverage badge for frigg/frigg-coverage" style="width: 200px;" />
</div>

In order to start reporting coverage from your test runs it is necessary to export the coverage report in a supported format and add coverage settings to the frigg configuration file. Example configuration of a python project:

{% highlight yaml %}
tasks:
 - coverage run --source=package runtests.py
 - coverage xml

coverage:
  path: coverage.xml
  parser: python
{% endhighlight %}

The `path` option is the path to the coverage file relative to the git root of the project and the parser option is the kind of parser needed to parse the file. The available options at this moment is `cobertura`, `clover` and `python`, where `python` is just an alias for cobertura since coverage.py uses the cobertura xml-schema.

The badge will change color based on the coverage percentage. The list below show the range for the different colors.

* coverage == 100: brightgreen
* coverage >= 90: green
* coverage >= 70: yellow
* coverage >= 50: orange
* coverage < 50: red

Go and show the world the coverage of your project. If you have a coverage format that you would like to see supported please [open an issue on frigg-coverage](https://github.com/frigg/frigg-coverage/issues) or send us an email at [hi@frigg.io](mailto:hi@frigg.io?subject=[frigg-coverage])
