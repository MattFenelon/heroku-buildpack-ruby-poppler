# heroku-buildpack-ruby-poppler

Builds the poppler library and installs on Heroku

## Usage

This buildpack works best with [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) so that it can be used with your app's existing buildpacks.

## Example

#### .buildpacks

    https://github.com/MattFenelon/heroku-buildpack-ruby-poppler
    https://github.com/heroku/heroku-buildpack-ruby

## Versions

The buildpack installs Poppler 0.38.

0.38 is the last released version to work with the latest version of the poppler
gem (3.0.7). See https://github.com/ruby-gnome2/ruby-gnome2/issues/653
for more information.

## Installation path

Poppler is installed to /app/vendor/poppler. The installation path is added
`LD_LIBRARY_PATH` so it can be found by linking programs.

## License

Apache License 2.0
