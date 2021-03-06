# Cloud Posse Build Harness [![Build Status](https://travis-ci.org/cloudposse/build-harness.svg)](https://travis-ci.org/cloudposse/build-harness)

This `build-harness` is a collection of Makefiles to facilitate building Golang projects, Dockerfiles, Helm charts, and more. 

It's designed to work with CI/CD systems such as Travis CI, CircleCI and Jenkins.

It's 100% Open Source and licensed under [APACHE2](LICENSE).


## Usage

At the top of your `Makefile` add, the following...

```make
-include $(shell curl -so .build-harness "https://raw.githubusercontent.com/cloudposse/build-harness/master/templates/Makefile.build-harness"; echo .build-harness)
```

This will download a `Makefile` called `.build-harness` and include it at run-time. We recommend adding the `.build-harness` file to your `.gitignore`.

This automatically exposes many new targets that you can leverage throughout your build & CI/CD process.

Run `make help` for a list of available targets.


## Makefile Targets

```bash
$ make help

Available targets:

  bash:lint                           Lint all bash scripts
  docker:build                        Build docker image
  docker:login                        Login into docker hub
  docs:copyright-add                  Add copyright headers to source code
  docs:toc-update                     Update table of contents in README.md
  geodesic:deploy                     Run a Jenkins Job to Deploy $(APP) with $(CANONICAL_TAG)
  git:aliases-update                  Update git aliases
  git:submodules-update               Update submodules
  github:download-release             Download release from github
  go:build                            Build binary
  go:build-all                        Build binary for all platforms
  go:clean                            Clean compiled binary
  go:clean-all                        Clean compiled binary and dependency
  go:deps                             Install dependencies
  go:deps-build                       Install dependencies for build
  go:deps-dev                         Install development dependencies
  go:fmt                              Format code according to Golang convention
  go:install                          Install cli
  go:lint                             Lint code
  go:test                             Run tests
  go:vet                              Vet code
  helm:install                        Install helm
  helm:repo:add-current               Add helm remote dev repos
  helm:repo:add-remote                Add helm remote repos
  helm:repo:build                     Build repo
  helm:repo:clean                     Clean helm repo
  helm:repo:fix-perms                 Fix repo filesystem permissions
  helm:repo:info                      Show repo info
  helm:repo:lint                      Lint charts
  helm:serve:index                    Build index for serve helm charts
  help                                This help screen
  jenkins:run-job-with-tag            Run a Jenkins Job with $(TAG)
  make:lint                           Lint all makefiles
  travis:docker-tag-and-push          Tag according travis envvars and push
```


## Real World Examples

- [`github-authorized-keys`](https://github.com/cloudposse/github-authorized-keys/) - A Golang project that leverages `docker:%`, `go:%`, `travis:%` targets
- [`charts`](https://github.com/cloudposse/charts/) - A collection of Helm Charts that leverages `docker:%` and `helm:%` targets
- [`bastion`](https://github.com/cloudposse/bastion/) - A docker image that leverages `docker:%` and `bash:lint` targets


## Help

**Got a question?** 

File a GitHub [issue](https://github.com/cloudposse/build-harness/issues), send us an [email](mailto:hello@cloudposse.com) or reach out to us on [Gitter](https://gitter.im/cloudposse/).

## Contributing

### Bug Reports & Feature Requests

Please use the [issue tracker](https://github.com/cloudposse/build-harness/issues) to report any bugs or file feature requests.

### Developing

If you are interested in being a contributor and want to get involved in developing the `build-harness`, we would love to hear from you! Shoot us an [email](mailto:hello@cloudposse.com).

In general, PRs are welcome. We follow the typical "fork-and-pull" Git workflow.

 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Commit** changes to your own branch
 4. **Push** your work back up to your fork
 5. Submit a **Pull request** so that we can review your changes

**NOTE:** Be sure to merge the latest from "upstream" before making a pull request!

Here's how to get started...

1. `git clone https://github.com/cloudposse/build-harness.git` to pull down the repository 
2. `make init` to initialize the [`build-harness`](https://github.com/cloudposse/build-harness/)
3. Review the [documentation](docs/) on compiling

## License

[APACHE 2.0](LICENSE) © 2016-2017 [Cloud Posse, LLC](https://cloudposse.com)

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at
     
      http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.

## About

GitHub Authorized Keys is maintained and funded by [Cloud Posse, LLC][website]. Like it? Please let us know at <hello@cloudposse.com>

We love [Open Source Software](https://github.com/cloudposse/)! 

See [our other projects][community] or [hire us][hire] to help build your next cloud-platform.

  [website]: http://cloudposse.com/
  [community]: https://github.com/cloudposse/
  [hire]: http://cloudposse.com/contact/
  
### Contributors


| [![Erik Osterman][erik_img]][erik_web]<br/>[Erik Osterman][erik_web] | [![Igor Rodionov][igor_img]][igor_web]<br/>[Igor Rodionov][igor_web] |
|-------------------------------------------------------|------------------------------------------------------------------|

  [erik_img]: http://s.gravatar.com/avatar/88c480d4f73b813904e00a5695a454cb?s=144
  [erik_web]: https://github.com/osterman/
  [igor_img]: http://s.gravatar.com/avatar/bc70834d32ed4517568a1feb0b9be7e2?s=144
  [igor_web]: https://github.com/goruha/


