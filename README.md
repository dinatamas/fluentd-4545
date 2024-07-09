Fluentd Issue 4545 - Reproduction
=================================

Reproduction Dockerfiles for https://github.com/fluent/fluentd/issues/4545.

## Good Scenario (Previous Behavior)

- `docker pull registry.suse.com/suse/sle15:15.6`
- `docker build -t fluentd.good -f Dockerfile.good .`
- `docker run --rm -it --name fluentd.good fluentd.good`

* Manually built ruby 3.3.1
* Requires `libopenssl-3-devel` to build ruby
* Bundler version 2.5.9
* `Gemfile3.3.lock`

## Bad Scenario (Reproduces Issue)

- `docker pull registry.suse.com/suse/sle15:15.6`
- `docker build -t fluentd.bad -f Dockerfile.bad .`
- `docker run --rm -it --name fluentd.bad fluentd.bad`

* Manually built ruby 2.5.9
* Requires `libopenssl-1_1-devel` to build ruby
* Bundler version 1.16.1
* `Gemfile2.5.lock`
