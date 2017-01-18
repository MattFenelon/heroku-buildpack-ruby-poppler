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

The buildpack installs [Poppler 0.42.0](https://poppler.freedesktop.org/releases.html)

0.42.0 is the last released version to work with the latest version of the poppler
gem [3.0.8](https://rubygems.org/gems/poppler/versions/3.0.8).

## Installation path

Poppler is installed on the dynos to `/app/vendor/poppler`. The installation
path is appended to the environment variable `LD_LIBRARY_PATH`, which is used
by other programs to find the shared library.

## License

Apache License 2.0
