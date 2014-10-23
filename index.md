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

#### `task`
Should be defined as a list of commands. Those commands will be run in the
order they are defined during the run.

#### `webhooks` - optional
Should be defined as a list of urls where frigg can post status about the
build.

#### `comment` - optional
If set to `false`, frigg will not comment on commits on Github only set commit
status in the Github API

### Example
{% highlight yaml %}
tasks:
  - tox
  - flake8

comment: false
{% endhighlight %}

## Approval
Since frigg is in a beta phase all projects need approval before they can be
built on. If you think it is taking way to long before your project is
approved you can send us a mail at hi@frigg.io.

## About Github permissions
We ask for write permissions to your repositories. We actually do not want to,
however there is no way around this. Github does not have a permission scope in
their API that gives read-only access to repositories. We try our best to keep
the scope of the permissions we ask for at a minimum.
