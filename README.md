# Checks API Plugin
[![Join the chat at https://gitter.im/jenkinsci/github-checks-api](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/jenkinsci/github-checks-api)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://issues.jenkins-ci.org/issues/?jql=component%20%3D%20checks-api-plugin)
[![Jenkins](https://ci.jenkins.io/job/Plugins/job/checks-api-plugin/job/master/badge/icon?subject=Jenkins%20CI)](https://ci.jenkins.io/job/Plugins/job/checks-api-plugin/job/master/)
[![GitHub Actions](https://github.com/jenkinsci/checks-api-plugin/workflows/CI/badge.svg?branch=master)](https://github.com/jenkinsci/checks-api-plugin/actions)
[![codecov](https://codecov.io/gh/jenkinsci/checks-api-plugin/branch/master/graph/badge.svg)](https://codecov.io/gh/jenkinsci/checks-api-plugin)

Inspired by the [GitHub Checks API](https://docs.github.com/en/rest/reference/checks#runs), this plugin aims to provide a general API to allow Jenkins plugins publishing checks (or reports) to remote source code management (SCM) platforms (e.g. GitHub, GitLab, BitBucket, etc.).

By consuming this API, other plugins can publish check with customized parameters for a Jenkins build, such as status, summary, warnings, code annotations, or even images.
Implementations of this API decide on how to make use of these parameters and where to publish the checks.

Known consumers:
* [Warnings Next Generation Plugin](https://plugins.jenkins.io/warnings-ng)
* [Code Coverage API Plugin](https://plugins.jenkins.io/code-coverage-api)

Implementations:
* [GitHub Checks Plugin](https://plugins.jenkins.io/github-checks)

## Embedded Features

### Build Status Check

![GitHub Status](docs/images/github-status.png)

By listening to the Jenkins builds, this plugin will automatically publish statuses (pending, in progress, and completed) to different SCM platforms based on the remote repository the build is using.

### Pipeline Usage

Instead of depending on consumers plugins, the users can publish their checks directly in the pipeline script:

```
publishChecks name: 'example', title: 'Pipeline Check', summary: 'check through pipeline', text: 'you can publish checks in pipeline script', detailsURL: 'https://github.com/jenkinsci/checks-api-plugin#pipeline-usage'
```

## Guides

- [Consumers Guide](docs/consumers-guide.md)
- [Implementation Guide](docs/implementation-guide.md)

## Acknowledgements

This plugin is started as a [Google Summer of Code 2020 project](https://summerofcode.withgoogle.com/projects/#5139745388101632), you can find more about it on [Jenkins GSoC SIG](https://www.jenkins.io/sigs/gsoc/).
