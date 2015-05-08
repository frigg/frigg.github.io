---
layout: docs
title: Running services
---

## Settings in .frigg.yml
This option activates services the project.

For instance, in order to run redis-server in the container where the project is tested.

{% highlight yaml %}
services:
  - redis-server
{% endhighlight %}

## Supported services
* redis-server
* mysql
* postgresql-server

If you need more services by default, please (file an issue)[https://github.com/frigg/docker-test-base/issues].

## Install and run custom services

It is possible to install and run custom services by using (setup tasks)[/docs/setup].
For instance, if you want apache2 to run in the container, you first need to install it and then start it.

{% highlight yaml %}
setup:
  - apt-get install apache2
  - /etc/init.d/apache2 start
{% endhighlight %}
