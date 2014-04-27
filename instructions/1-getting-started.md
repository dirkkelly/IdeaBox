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

#### Create `config.ru`

To start our server we need a configuration file, we'll leave it empty for now.

```
```

![create file](https://cloud.githubusercontent.com/assets/81055/2811901/e0d27758-ce37-11e3-8c0b-d7ebdd81ddf4.png)


#### Start Your Server

>
```
rackup
```

![missing run statement](https://cloud.githubusercontent.com/assets/81055/2811893/61c9f800-ce37-11e3-982a-bb6c33b14b0e.png)

>
**Missing run or map statement**

#### Update `config.ru`

We've created the config file, but rack doesn't know which app to run. Let's tell it to run **IdeaBoxApp**.

```
run IdeaBoxApp
```

Let's tell it that we want to run an app called **IdeaBoxApp**

>
```
rackup
```

**Unitialized constant IdeaBoxApp**

Still no good, looks like we need to create an application called IdeaBoxApp.

#### Create The File `app.rb`

We're going to create a really simple Sinatra application to get started.

```
class IdeaBoxApp < Sinatra::Base
end
```

#### Update the file `config.ru`

We need to tell rack where to find that file

```
require './app'

run IdeaBoxApp
```

**Uniitialized constant Sinatra**

### Create the file  `Gemfile`

```
source 'https://rubygems.org'

gem 'sinatra', require: 'sinatra/base'
```

>
![Gemfile](https://cloud.githubusercontent.com/assets/81055/2811862/4111001a-ce35-11e3-8d97-5e270c70e672.png)

_don't forget to save your file_

### Download the gems with Bundler

>
```
bundle
```

![bundle](https://cloud.githubusercontent.com/assets/81055/2811859/266025d4-ce35-11e3-8969-c2552278a13f.png)

### Start the server from the terminal

```
rackup
```

**unitialized constant IdeaBoxApp (NameError)**

Oh no, looks like rack doesn't know how to find `IdeaBoxApp`

Let's tell rack 
