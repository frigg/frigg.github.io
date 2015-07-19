---
layout: docs
title: Preview
---

Preview makes it possible to deploy live versions of your pull-requests.
It enables you to run your application within an docker container and use
just as if you deployed it yourself. It makes evaluation of pull-requests
on web application a charm.

### Setup

The setup is just to add a configuration to your .frigg.yml file. Firstly,
a Docker image must be set in the settings file. This setting tells Frigg
that it should initiate a Preview deployment. Add the following to your
.frigg.yml:

{% highlight yaml %}
preview:
  image: frigg/frigg-test-base
{% endhighlight %}

There are some restrictions on the allowed Docker images. See the Docker
image section below for a list of allowed images.

Furthermore, it is necessary to define tasks that should be run when the
Docker container is created. The important part here is that the last task
should be start a daemon that listens to port 8000. If it is not a daemon
the docker container will be stopped and if it is not listening to port 8000
the application will not be accessible from the outside.

Below is an example from running frigg-hq with preview.
{% highlight yaml %}
preview:
  image: frigg/frigg-test-base
  tasks:
   - pip install -r requirements.txt
   - createdb frigg
   - python3 manage.py migrate
   - gunicorn -D -b 0.0.0.0:8000 frigg.wsgi
{% endhighlight %}


### Allowed Docker containers

* All images with the `frigg/`-prefix

### Restricting access to the deployed preview
There is no support, yet, for authentication in the Frigg Preview layer.
Thus, if a preview would contain sensitive information or secret product
previews then the authentication must be handled by the application itself.
