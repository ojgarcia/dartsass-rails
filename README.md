# Dart Sass for Rails

[Sass](https://sass-lang.com) is a stylesheet language that’s compiled to CSS. It allows you to use variables, nested rules, mixins, functions, and more, all with a fully CSS-compatible syntax.

This gem wraps [the standalone executable version](https://github.com/sass/dart-sass/releases) of the Dart version of Sass. These executables are platform specific, but included in this gem are the ones for macOS, Linux, and Windows. The Linux and Windows versions are the ones for 64-bit, and the macOS version is compiled for Intel but will run on ARM as well.

The installer will create your Sass input file in `app/assets/stylesheets/application.scss`. This is where you should import all the style files to be compiled [using the @use rule](https://sass-lang.com/documentation/at-rules/use). When you run `rails dartsass:build`, this input file will be used to generate the output in `app/assets/builds/application.css`. That's the output CSS that you'll include in your app.

If you need to use a custom input or output file, you can run `bundle exec dartsass` to access the platform-specific executable, and give it your own build options.

When you're developing your application, you want to run Dart Sass in watch mode, so changes are automatically reflected in the generated CSS output. You can do this either by running `rails dartsass:watch` as a separate process, or by running `./bin/dev` which uses [foreman](https://github.com/ddollar/foreman) to starts both the Dart Sass watch process and the rails server in development mode.


## Installation

1. Run `./bin/bundle add dartsass-rails`
2. Run `./bin/rails dartsass:install`


## Building in production

The `dartsass:build` is automatically attached to `assets:precompile`, so before the asset pipeline digests the files, the Dart Sass output will be generated.


## Version

Dart Sass 1.49.0


## License

Dart Sass for Rails is released under the [MIT License](https://opensource.org/licenses/MIT).
Sass is released under the [MIT License](https://opensource.org/licenses/MIT).
