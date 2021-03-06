# Heroku Goon Buildpack

This is a [Heroku buildpack][0] for bundling a compatible [goon][1] binary with your environment.

## Versions

* Buildpack:   `0.1`
* goon: `1.1.1`

## Usage

This buildpack only installs goon, it isn't very useful by itself. You'll probably want to use it as part of a multi-buildpack. Here is an example using the Ruby buildpack.

```bash
$ heroku buildpacks:set 'https://github.com/heroku/heroku-buildpack-multi.git'
$ echo 'https://github.com/heroku/heroku-buildpack-ruby.git' >> .buildpacks
$ echo 'https://github.com/amberbit/heroku-buildpack-goon.git' >> .buildpacks
$ git add .buildpacks
$ git commit -m 'Add multi-buildpack'
```

[0]: http://devcenter.heroku.com/articles/buildpacks
[1]: https://github.com/alco/goon

## Troubleshooting

If you run into issues when trying to deploy with this buildpack, make sure your app is running on Cedar with Ubuntu 14.04 (`cedar-14`). You can check this with:

```bash
$ heroku stack
```

If you are on an older stack, you can upgrade to `cedar-14` with:

```bash
$ heroku stack:set cedar-14
```

## Credits

This buildpack is based upon awesome
(wkhtmltopdf-buildpack)[https://github.com/dscout/wkhtmltopdf-buildpack]

