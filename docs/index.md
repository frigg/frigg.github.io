---
layout: docs
title: Documentation
---

## Configuration file
Frigg works without setup for some projects. However, you might want to
have a more specific configuration. We support configuration through a
yaml file. If you put `.frigg.yml` in the base of your repository Frigg
will read it and use those settings while testing and building your
project.

### Options

#### `task`
Should be defined as a list of commands. Those commands will be run in the order they are
defined during the run.

#### `webhooks` - optional
Should be defined as a list of urls where frigg can post status about the build.

#### `comment` - optional
If set to `false`, frigg will not comment on commits on Github only set commit status in the Github API

### Example
{% highlight yaml %}
tasks:
  - tox
  - flake8

comment: false
{% endhighlight %}
