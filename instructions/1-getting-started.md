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

We're going to create a really simple Sinatra application to get started, let's create an **app.rb** file.

```ruby
# app.ry

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

And rack needs to know to load the gems

```ruby
# config.ru 

require 'bundler'
Bundler.require

require './app'

run IdeaBoxApp
```

Now let's download those files with the bundle command.

>
```
bundle
```

![bundle](https://cloud.githubusercontent.com/assets/81055/2811961/fa417a2e-ce3a-11e3-83f6-9593b6b4949a.png)

>
```
rackup
```

>
**Error: you may be using the wrong PORT & HOST for your server app**

Because we're developing on Cloud9 we need to specify the server and port for the application.

>
```
rackup -p $PORT -o $IP
```

![rackup](https://cloud.githubusercontent.com/assets/81055/2811971/894f4db8-ce3b-11e3-8ae5-d1098995fbc8.png)

Let's visit the url to see our website.

![doesn't know](https://cloud.githubusercontent.com/assets/81055/2811984/d0ac6c86-ce3b-11e3-879a-5eefb2ff0578.png)

We're so close, the server is running, but the application doesn't have any content, let's try adding a hello world.

```ruby
# app.rb

class IdeaBoxApp < Sinatra::Base
  get '/' do
    'Hello, world!'
  end
end
```

#### Restart the server

In order for the changes to work, you need to reboot your rack server.

**Protip: You can end the server by press ctrl+c**

#### Hello World

![hello world](https://cloud.githubusercontent.com/assets/81055/2811990/0afca1d0-ce3c-11e3-8b2d-2ad751bdb61d.png)

### End of Part One

![its_working_star_wars](https://cloud.githubusercontent.com/assets/81055/2811974/a482c38a-ce3b-11e3-833f-23503bb62e8d.gif)

#### Save Our Work to Github

Now it's time to save our work and update Github.

>
```
git status
```

**You should have four unstaged files**

>
```
git add Gemfile
git add Gemfile.lock
git add config.ru
git add app.rb
```

_You can also add all file with `git add -A` where -A means "all unstaged files_

Now we need to commit this work with a message

>
```
git commit -m "Created IdeaBox app"
```

And we need to push all those changes back to Github (refered to as origin)

>
```
git push origin
```
```
