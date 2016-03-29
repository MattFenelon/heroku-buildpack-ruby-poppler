# heroku-buildpack-ruby-poppler

Builds the poppler library and installs the poppler gem, for use by Ruby

## Versions

This buildpack installs Poppler 0.38.

0.38 is the last released version to work with the latest version of the poppler
gem (3.0.7). See https://github.com/ruby-gnome2/ruby-gnome2/issues/653
for more information.

## Usage

This buildpack works best with [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) so that it can be used with your app's existing buildpacks.

## Example

#### .buildpacks

    https://github.com/MattFenelon/heroku-buildpack-ruby-poppler
    https://github.com/heroku/heroku-buildpack-ruby

## License

Apache License 2.0
