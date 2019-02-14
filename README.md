# Todos API

A sample application to learn Rails API development:

https://scotch.io/tutorials/build-a-restful-json-api-with-rails-5-part-one

## Scaffold API

```bash
$ dc run dev
$ gem install rails
$ rails new todos-api --database=postgresql --api -T
```

## Configure Testing Tools

Add `rspec-rails`, `factory_bot_rails`, `shoulda_matchers`, `faker` and `database_cleaner` to the Gemfile.

```bash
$ cd todos-api
$ bundle install
$ rails generate rspec:install
$ mkdir spec/factories
```

## Setup Spring and Guard for RSpec

Add `spring-commands-rspec` and `guard-rspec` to the Gemfile.

```bash
$ bundle install
$ bundle exec spring binstub rspec
$ bundle exec guard init rspec
```

Edit the `Guardfile` to use `bin/rspec` as the command. 

```bash
$ bundle exec guard
```

Configure `spec/rails_helper.rb` to work with Shoulda, FactoryBot and DatabaseCleaner.

## Setup Postgres

Add the following settings to `config/database.yml`:

```yaml
host: db
username: postgres
```

Then create the database:

```bash
$ rake db:create
```

## Models

```bash
$ rails g model Todo title:string created_by:string
$ rails g model Item name:string done:boolean todo:references
$ rake db:migrate
```

## Controllers

```bash
$ rails g controller Todos
$ rails g controller Items
```

## Testing

```bash
# GET /todos
$ http :3000/todos
# POST /todos
$ http POST :3000/todos title=Colin created_by=1
# PUT /todos/:id
$ http PUT :3000/todos/1 title=ColinTheGeek
# DELETE /todos/:id
$ http DELETE :3000/todos/1
```