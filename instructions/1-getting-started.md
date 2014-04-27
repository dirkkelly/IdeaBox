# Getting Started

## Environment Setup

For this project you will need a **Ruby on Rails** workspace on [**Cloud 9**](http://c9.io/)

### Create the file  `Gemfile`

```
source 'https://rubygems.org'

gem 'sinatra', require: 'sinatra/base'
```

![gemfile](https://cloud.githubusercontent.com/assets/81055/2811852/b750b406-ce34-11e3-9ebf-41519cd1e835.gif)

_don't forget to save your file_

### Download the gems

>
```
bundle
```

### Create the file `config.ru`

```
require 'bundler'
Bundler.require

run IdeaBoxApp
```

### Create the file `app.ry`

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

### Start the server from the terminal

>
```
rackup -p $PORT -o $IP
```
