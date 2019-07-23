# Capistrano::Mongoid

Welcome to your new gem! In this directory, you'll find the files you need to be able to package up your Ruby library into a gem. Put your Ruby code in the file `lib/capistrano/mongoid`. To experiment with that code, run `bin/console` for an interactive prompt.

TODO: Delete this and the text above, and describe your gem

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'mongoid', git: "https://github.com/xuxiangyang/mongoid.git"
gem 'capistrano-mongoid'
```

I'm waiting for https://github.com/mongodb/mongoid/pull/4650 PR be merged, before this PR merged, you must use my mongoid fork.

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install capistrano-mongoid

## Usage

```ruby
# Capfile
require 'capistrano/sidekiq'
require 'capistrano/sidekiq/monit' #to require monit tasks # Only for capistrano3
```

Configurable options, shown here with defaults:

```ruby
mongoid_role => "mongoid" # sync index and shard server, should has only one server
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/capistrano-mongoid. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the Capistrano::Mongoid project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/[USERNAME]/capistrano-mongoid/blob/master/CODE_OF_CONDUCT.md).
