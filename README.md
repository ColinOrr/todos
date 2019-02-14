# Todos API

A sample application to learn Rails API development:

https://scotch.io/tutorials/build-a-restful-json-api-with-rails-5-part-one

## API Setup

```bash
$ dc run dev
$ gem install rails
$ rails new todos-api --database=postgresql --api -T
```

Add `rspec-rails`, `factory_bot_rails`, `shoulda_matchers`, `faker` and `database_cleaner` to the Gemfile.

```bash
$ cd todos-api
$ bundle install
$ rails generate rspec:install
$ mkdir spec/factories
```

Configure `spec/rails_helper.rb` to work with Shoulda, FactoryBot and DatabaseCleaner.