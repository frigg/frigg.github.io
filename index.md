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

## Badges
Example badge for frigg/frigg [![Build status](https://ci.frigg.io/badges/frigg/frigg/)](https://ci.frigg.io/frigg/frigg/last/)

To get a nice build badge in your readme to show everyone that you build is a success, or warn people that it is broken and the master branch might not work at the moment, just add the code below.

#### Markdown
```markdown
[![Build status](https://ci.frigg.io/badges/<owner>/<repo>/)](https://ci.frigg.io/<owner>/<repo>/last/)
```

#### reStructuredText
```rst
.. image:: https://ci.frigg.io/badges/<owner>/<repo>/
     :target: https://ci.frigg.io/<owner>/<repo>/last/
     :alt: Build Status
```

#### RDoc
```rdoc
{<img src="https://ci.frigg.io/badges/<owner>/<repo>/" alt="Build Status" />}[https://ci.frigg.io/<owner>/<repo>/last/]
```

#### HTML
```html
<a href="https://ci.frigg.io/<owner>/<repo>/last/"><img src="https://ci.frigg.io/badges/<owner>/<repo>/" alt="Build Status" /></a>
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
