# Getting Started

## Start a Terminal

The default terminal down the bottom has a tendency to crash, start a full screen terminal to get started.

Press **cmd + t** to open a full sreen terminal

### Hello World

We're going to build a [Sinatra](http://www.sinatrarb.com/) application, because [**Cloud 9**](http://c9.io/) is a
bit different to a normal environment we're going to need to use `rackup` to start our server.

#### Start Your Server

Sinatra is a rack application, to start a rack application we use the command `rackup`

>
```
rackup
```

![missing config.ru](https://cloud.githubusercontent.com/assets/81055/2811881/bac3518c-ce36-11e3-982d-0992e6341e75.png)

> 
**config.ru not found**

#### Create Config File

To start our server we need a configuration file, we'll leave it empty for now.

```ruby
# config.ru
```

![config ru](https://cloud.githubusercontent.com/assets/81055/2811947/f51c8a08-ce39-11e3-987c-5d432b0f1486.gif)

>
```
rackup
```

![missing run statement](https://cloud.githubusercontent.com/assets/81055/2811893/61c9f800-ce37-11e3-982a-bb6c33b14b0e.png)

>
**Missing run or map statement**

We've created the config file, but rack doesn't know which app to run. Let's tell it to run **IdeaBoxApp**.

```ruby
# config.ru

run IdeaBoxApp
```

>
```
rackup
```

>
**Unitialized constant IdeaBoxApp**

Still no good, looks like we need to create an application called IdeaBoxApp.

#### Create Application file.

We're going to create a really simple Sinatra application to get started.

```ruby
# app.rb

class IdeaBoxApp < Sinatra::Base
end
```

We also need to tell rack where to find that file

```ruby
# config.ru 

require './app'

run IdeaBoxApp
```

>
```
rackup
```

>
**Uniitialized constant Sinatra**

IdeaBoxApp relies on Sinara so we're going to need to create a Gemfile which specifies this dependency

```ruby
# Gemfile

source 'https://rubygems.org'

gem 'sinatra', require: 'sinatra/base'
```

Now let's download those files with the bundle command.

>
```
bundle
```

![bundle](https://cloud.githubusercontent.com/assets/81055/2811859/266025d4-ce35-11e3-8969-c2552278a13f.png)

### Start the server from the terminal


>
```
rackup
```
