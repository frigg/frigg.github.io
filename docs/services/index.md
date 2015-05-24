---
layout: docs
title: Running services
---

Frigg support running services installed into the docker image in use,
however, they must be started before the test run either by the [services
option](/docs/configuration/#services---optional) in the .frigg.yml file or
by a [setup task](/docs/configuration/#setuptasks---optional).

{% highlight yaml %}
services:
  - redis-server
{% endhighlight %}

## Supported services
* docker
* memcached
* mongodb
* mysql
* postgresql
* redis-server

If you need more services by default, please
[open an issue](https://github.com/frigg/docker-test-base/issues).

## Install and run custom services

It is possible to install and run custom services by using
[setup tasks](/docs/setup/). For instance, if you want apache2 to run
in the container, you first need to install it and then start it.

{% highlight yaml %}
setup:
  - apt-get install apache2
  - /etc/init.d/apache2 start
{% endhighlight %}

## Usage of services
Most services has default settings and can be used according to their
documentation. The build runs within a Docker container and has root access
to that container, by which makes it possible to configure the services
as you want. We encourage you to do this kind of setup in
[setup-tasks](/docs/configuration/#setuptasks---optional).

The sections below lists special requirements when working with different
services.

### `postgresql`
Postgresql should be used without providing username and password for
authentication as postgresql is set up to authenticate with the current
unix user. If you need to setup databases or extra roles this can be
accomplished by using `psql`.
