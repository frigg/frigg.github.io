---
layout: docs
title: Badges
---

## Badges

### Build badge [![Example badge for frigg/frigg](https://ci.frigg.io/frigg/frigg.svg)](https://ci.frigg.io/frigg/frigg/last/)

To get a nice build badge in your readme to show everyone that you build is a success, or warn people that it is broken and the master branch might not work at the moment, just add the code below.

#### Markdown
{% highlight markdown %}
[![Build status](https://ci.frigg.io/<owner>/<repo>.svg)](https://ci.frigg.io/<owner>/<repo>/last/)
{% endhighlight %}

#### reStructuredText
{% highlight rst %}
.. image:: https://ci.frigg.io/<owner>/<repo>.svg
     :target: https://ci.frigg.io/<owner>/<repo>/last/
     :alt: Build Status
{% endhighlight %}

#### HTML
{% highlight html %}
<a href="https://ci.frigg.io/<owner>/<repo>/last/">
  <img src="https://ci.frigg.io/<owner>/<repo>.svg" alt="Build Status" />
</a>
{% endhighlight %}


### Coverage badge [![Example badge for frigg/frigg](https://ci.frigg.io/frigg/frigg/coverage.svg)](https://ci.frigg.io/frigg/frigg/last/)

To get a nice build badge in your readme to show everyone that you build is a success, or warn people that it is broken and the master branch might not work at the moment, just add the code below.

#### Markdown
{% highlight markdown %}
[![Build status](https://ci.frigg.io/<owner>/<repo>/coverage.svg)](https://ci.frigg.io/<owner>/<repo>/last/)
{% endhighlight %}


#### reStructuredText
{% highlight rst %}
.. image:: https://ci.frigg.io/<owner>/<repo>/coverage.svg
     :target: https://ci.frigg.io/<owner>/<repo>/last/
     :alt: Build Status
{% endhighlight %}


#### HTML
{% highlight html %}
<a href="https://ci.frigg.io/coverage/<owner>/<repo>/last/">
  <img src="https://ci.frigg.io/<owner>/<repo>.svg" alt="Build Status" />
</a>
{% endhighlight %}
