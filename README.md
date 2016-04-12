# heroku-buildpack-ruby-poppler

Builds the poppler library and installs on Heroku

## Usage

This buildpack works best with [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) so that it can be used with your app's existing buildpacks.

## Example

#### .buildpacks

    https://github.com/MattFenelon/heroku-buildpack-ruby-poppler
    https://github.com/heroku/heroku-buildpack-ruby

## Versions

The buildpack installs Poppler 0.42.0

0.42.0 is the last released version to work with the latest version of the poppler
gem (3.0.8).

## Installation path

Poppler is installed to ``/app/vendor/poppler`. The installation path is appended
`LD_LIBRARY_PATH`, which is used by other programs to find the shared library.

## License

Apache License 2.0
