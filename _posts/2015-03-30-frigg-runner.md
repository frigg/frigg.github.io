---
layout: post
author: relekang
title: Frigg runner
category: Features
slug: frigg-runner
---

Frigg knows which tasks a project needs done in order to check the status of the
project. It can be everything from running tests to running linters. Frigg gets
the tasks either from the frigg settings file or by guessing based on the files
in the project. We thought that it would be great to have a easy way of running
all tasks locally. As a result we created
[frigg-runner](https://github.com/frigg/frigg-runner), which uses the same task
discovery functionality as the CI-workers.

Install it with `pip install frigg-runner`, or with [pipsi](https://github.com/mitsuhiko/pipsi),
and then run it with `frigg`. If you run `frigg --help` you will get the help
listed below, in which you can find the options supported by frigg-runner.

    $ frigg --help
    Usage: frigg [OPTIONS]

    Options:
      -f, --failfast  Exit if one of the tasks returns other than statuscode 0.
      -v, --verbose   Print output from every task.
      -p, --path      Working directory, the path where the frigg-file lives.
      --help          Show this message and exit.
