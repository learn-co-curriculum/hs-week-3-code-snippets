---
tags: active record, kids, ruby, advanced, code snippets
language: ruby
level: 2
type: code snippets
---

## A pinch of delicious, delicious code

Here is the code that you will need to add to your application to get set up with ActiveRecord.

### Gemfile
(These should go right below your sinatra gem.)

```ruby 
gem "activerecord"
gem "sinatra-activerecord"
gem "rake"
```

We also need to add the sqlite3 gem to your `development` group so that it looks like this:

```ruby
group :development do
  gem "pry"
  gem "tux"
  gem "sqlite3"
end
```

### Rakefile

This code is all you need in your Rakefile for now:

```ruby
require 'sinatra/activerecord/rake' 
require './config/environment' 
```

The rake gem automatically provides all of the rake tasks (commands) that you need to build your database. Type `rake -T` in the terminal to see a list of available commands.

### environment.rb
(In the config directory. This should go right below `Bundler.require`.)

```ruby
configure :development do
  set :database, "sqlite3:db/database.db"
end
```

This sets up a connection to the database we will be creating.

### tweet.rb 
(in the app/models directory)

This is all the code that you need to create new tweets, add tweets to your database, pull saved tweets from the database and to view and change all of the tweets attributes (like user and status).

```ruby
class Tweet < ActiveRecord::Base

end
```

Your tweet class inherits all of that functionality (and more!) from the Active Record gem. Thank you Active Record!

### Did you miss class?

If you missed class, go check out the Study Guide. It will walk you through setting up your database and creating tables to store your data.

