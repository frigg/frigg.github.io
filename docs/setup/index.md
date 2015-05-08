---
layout: docs
title: Setup tasks
---

This section is dedicated to the setup tasks, they will be run before any other task and reported in a separate section on frigg.io.
In this example, Frigg will first build the maven project (and report it as a setup task), then run the tests as a separate task.

The benefit of using setup tasks is to separate the building steps from tests (to make a more clean report).

{% highlight yaml %}
setup_tasks:
  mvn -B build
tasks:
  mvn -B test
{% endhighlight %}
