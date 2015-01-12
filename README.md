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

### Rakefile

```ruby
require 'sinatra/activerecord/rake' 
require './config/environment' 
```

### tweet.rb (in the app/models directory)

This is all the code that you need to create new tweets, add tweets to your database, pull saved tweets from the database and to view and change all of the tweets attributes (like user and status). Your tweet class inherits all of that functionality (and more!) from the Active Record gem. Thank you Active Record!

```ruby
class Tweet < ActiveRecord::Base

end
```


