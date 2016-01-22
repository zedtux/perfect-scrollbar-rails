# perfect-scrollbar-Rails

This Gem integrates [noraesae](https://github.com/noraesae)'s [perfect-scrollbar](https://github.com/noraesae/perfect-scrollbar/) to your Rails project.

## Installation

Add this line to your application's Gemfile:

    gem 'perfect-scrollbar-rails'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install perfect-scrollbar-rails

## Usage

This gem uses a Rails Engine to make perfect-scrollbar's assets available to you.

Require the JavaScript files from your `application.js` or wherever needed using:

```
//= require perfect-scrollbar
```

Require the CSS files from your `application.scss` or wherever needed using:

```
*= require perfect-scrollbar
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
