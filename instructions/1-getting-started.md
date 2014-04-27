# Getting Started

## Environment Setup

For this project you will need a **Ruby on Rails** workspace on [**Cloud 9**](http://c9.io/)

## Create the file  `Gemfile`

```
source 'https://rubygems.org'

gem 'sinatra', require: 'sinatra/base'
```

## Create the file `config.ru`

```
require 'bundler'
Bundler.require

run IdeaBoxApp
```

## Create the file `app.rb`

```
require 'bundler'
Bundler.require

class IdeaBoxApp < Sinatra::Base
  get '/' do
    "Hello, World!"
  end

  run! if app_file == $0
end
```
