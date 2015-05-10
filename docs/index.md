---
layout: docs
title: Documentation
---

### Getting started
For Frigg to work with your project, follow these three simple steps.

#### `1. Add Github Webhook`

1. Go to your project repository on Github
2. Click *Settings*
3. Click *Webhooks & Services*
4. Click *Add Webhook*

5. Add `http://ci.frigg.io/webhooks/github/` as the *Payload URL*
6. Set *Content Type* to `application/json`
7. Click on *Send me everything*
8. Click *Update webhook*

From now on, when you push you code changes to Github, Frigg will build and test the code.

#### `2. Create .frigg.yml`
Frigg supports a number of languages and frameworks out of the box by [detecting common project files](/docs/configuration/detect-test-runners/) in the code.
However, if you want more steps than just running `mvn test` or `tox`, it is recommended to [create a .frigg.yml file](/docs/configuration/).

#### `3. Login`
Visit [ci.frigg.io](https://ci.frigg.io/) and click `Login` in the upper most right corner to sign in.
By signing in, Frigg will be able to build your private projects,
and only users with permissions to view the repository will be able to see the build and test status for the builds.

### Approval
Since Frigg is in a beta phase all projects need approval before they can be
built on. If you think it is taking way to long before your project is
approved you can send us a mail at hi@frigg.io.

### About Github permissions
We ask for write permissions to your repositories. We actually do not want to,
however there is no way around this. Github does not have a permission scope in
their API that gives read-only access to repositories. We try our best to keep
the scope of the permissions we ask for at a minimum.

