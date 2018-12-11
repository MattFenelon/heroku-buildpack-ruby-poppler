# heroku-buildpack-ruby-poppler

A Heroku buildpack for the [poppler](https://poppler.freedesktop.org/) library
for use with the [poppler](https://rubygems.org/gems/poppler/) gem.

## Usage

You can add additional buildpacks to your Heroku application with the
`buildpacks:add` command.

```shell
$ heroku buildpacks:add https://github.com/MattFenelon/heroku-buildpack-ruby-poppler --index 1
```

The index is set to 1 to install the poppler library before it is needed by
another buildpack, i.e. when bundler runs as part of the ruby
buildpack.

## Versions

The buildpack installs [Poppler 0.59.0](https://poppler.freedesktop.org/releases.html)

0.59.0 works with the latest version of the poppler
gem [3.1.8](https://rubygems.org/gems/poppler/versions/3.1.8).

## Compilation

The first-run of this buildpack will compile the poppler library. The
compilation of the poppler library can take some time. Subsequent
builds use a cached version of the compiled library, vastly decreasing the
amount of time to install the buildpack.

When the cache can't be used, the poppler library will need to be
compiled again. This could happen when the poppler version has changed, or there
have been enough changes to this buildpack that old cached versions can't be
used.

## Installation path

Poppler is installed on the dynos to `/app/vendor/poppler`. The installation
path is appended to the environment variables `LD_LIBRARY_PATH` and
`PKG_CONFIG_PATH`, which are used to find the shared libraries.

## License

Copyright 2017-2018 Matthew Fenelon

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
