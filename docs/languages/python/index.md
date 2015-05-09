---
layout: docs
title: Building python projects with frigg.io
---

Below you will find our view on best practices for using frigg.io
in your python projects.

## Tox
Tox is a great way to handle testing of several python versions
and several versions of your other dependencies. Define your tox
settings in tox.ini and list your different test environments with
`tox -l`. Each line in that output can be run specifically with
`tox -e <env>`. If you define a Frigg task for each of those environments
it will be easy to find errors on different versions when building
on frigg. Below you will find an example on a tox environment list
and the .frigg.yml to define them as separate tasks.

#### Tox environments
    $ tox -l
     py27
     py33
     py34

#### .frigg.yml
{% highlight yaml %}
tasks:
 - tox -e py27
 - tox -e py33
 - tox -e py34
{% endhighlight %}

## PEP8
We all like to follow the pep8 styleguide. It makes the project cleaner
and more friendly to collaboration. At frigg.io we use flake8 to detect
whenever our code is not compliant with pep8. To activate it add `flake8`
as a task in your .frigg.yml and add the following to tox.ini:

    [flake8]
    exclude=.tox

We want to exclude the .tox cache folder, because it contains all our
dependencies and not all projects follow pep8.
