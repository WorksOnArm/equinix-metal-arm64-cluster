# Continuous Integration (CI) on arm64 at Packet

This handy guide lists a set of CI and build systems that have been known to work
on arm64, with examples of projects that are successfully using them.
In addition, it notes some issues that are outstanding on some build systems
and efforts to address them.

If you are changing this file, please date stamp your changes. 
You can safely assume that any report more than 6 months old
is out of date.

Ed Vielmetti, Works on Arm, written 2018-08-06, updated 2019-02-21

### bazel

[Bazel](https://bazel.build/) is a build system derived from Google's internal "Blaze" system.
Notably it is the build system used for Tensorflow, a math library used for machine learning.
Work is [underway as of August 2018](https://github.com/WorksOnArm/cluster/issues/102)
to port Bazel and its rule sets to arm64.

### buildbot

[Buildbot](https://buildbot.net/) is a continuous integration framework.

### Buildkite

[Buildkite](https://www.buildkite.com) is a platform for running fast, secure, and 
scalable continuous integration pipelines on your own infrastructure.
The buildkite agent is a small, reliable and cross-platform build runner 
that makes it easy to run automated builds on your own infrastructure. 

### CircleCI

[CircleCI](https://circleci.com/) is a a modern continuous integration and continuous delivery (CI/CD) platform.

### CMake

[CMake](https://cmake.org/) is an open-source, cross-platform family of tools designed to build, test and package software.

### Codefresh

[Codefresh](https://codefresh.io/) is a continuous delivery platform built for Kubernetes. 
Once you create a free account, you can [enable ARM support](https://codefresh.io/docs/docs/incubation/arm-support/) 
and start building Docker images for ARM. There is no other special configuration needed. 
All Codefresh features (unit/integration tests, private Docker registry, on-demand demo 
environments, HELM/Kubernetes deployments etc.) are fully available for ARM builds.

### Github

Github is a source code management system with integrations into many
CI systems. Projects managed on Github can interface with CI through
use of webhooks to trigger build events.

* http://www.gihtub.com
* https://github.com/marketplace/category/continuous-integration

### Gitlab

GitLab is an application for all stages of the DevOps lifecycle. GitLab 
enables Concurrent DevOps, unlocking organizations from the constraints 
of the toolchain. 

[GitLab Runner](https://docs.gitlab.com/runner/) is the open source project 
that is used to run your jobs and send the results back to GitLab. It is 
used in conjunction with GitLab CI, the open-source continuous integration 
service included with GitLab that coordinates the jobs.

There is a community supported [ARM Docker image](https://gitlab.com/ulm0/gitlab-runner) 
so that your Raspberry PI can become a gitlab-runner too (and then, you will be able 
to run your ARM jobs on your machine as soon as you commit on Gitlab). Official 
support is pending the resolution of [merge request 725](https://gitlab.com/gitlab-org/gitlab-runner/merge_requests/725),
and some people are using that fork to provide arm64 runner support.

### Jenkins

Jenkins is a self-contained, open source automation server which can be 
used to automate all sorts of tasks related to building, testing, and 
delivering or deploying software. Jenkins can be installed through native 
system packages, Docker, or even run standalone by any machine with a Java 
Runtime Environment (JRE) installed. It can be used with 
[Github](https://jenkins.io/solutions/github/).

### Open Build Service (OBS)

### OpenHPC

OpenHPC is a Linux Foundation collaborative project that provides a 
variety of common, pre-built ingredients required to deploy and manage 
a HPC Linux cluster including provisioning tools, resource management, 
I/O clients, runtimes, development tools, and a variety of scientific 
libraries. We currently support ARM and x86_64 on two OS distributions. 
Any site interested in deploying an HPC cluster on ARM can potentially 
benefit from one or more packaged components and/or validated installation recipes.

The build system is based on a standalone instance of the Open Build 
Service that is at https://build.openhpc.community. A c1.large.arm instance 
is used to run OpenSUSE for the OBS build farm to support dedicated ARM builds.

### Shippable

Shippable's DevOps Automation platform gives you an easy way to set up 
Continuous Integration (CI) for your projects and automate unit testing, 
packaging, and deployment for any change in your source control repository 
(i.e. Github). As soon as your project is open-source, you just have to 
open an account at Shippable, add a `shippable.yml` file to your repo, 
add a link from your Shippable account to your github repo, and you're done, 
you can [build](https://github.com/gounthar/docker-adb/tree/stretch) on ARM64.

The only drawback is that you can't build ARM Docker images on it, 
or not easily. The [documentation](http://docs.shippable.com/platform/tutorial/workflow/run-ci-builds-on-arm/) 
is very well done.

As of February 2019, [Shippable is part of JFrog](https://techcrunch.com/2019/02/21/jfrog-acquires-shippable-adding-continuous-integration-and-delivery-to-its-devops-platform/).

### Travis CI

Travis CI is a hosted, distributed continuous integration service 
used to build and test software projects hosted at GitHub.
Open source projects may be tested at no charge via travis-ci.org. 
Private projects may be tested at travis-ci.com on a fee basis.

With Travis CI, you can't natively build on ARM architecture, but you 
can use [cross-compiling](https://github.com/gounthar/minitouch/blob/master/.travis.yml). [
ZeroMQ](https://github.com/zeromq/zeromq.js/) uses it in the prebuild phase. 
It is easily linked to your github repository by creating a `.travis-ci.yml` 
file, and linking your Github repository to your Travis account. 
The [documentation](https://docs.travis-ci.com/user/getting-started/) is pretty helpful.

As of January 2019, [Travis CI is part of Idera](https://blog.travis-ci.com/2019-01-23-travis-ci-joins-idera-inc).

### VSTS

VSTS is Visual Studio Team Services, a Microsoft product.
