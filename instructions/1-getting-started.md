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

In order to start our server with `rackup` we need a simple configuration file which will tell rack which application we want to run.

**Looks like we need to create a `config.ru` file**

#### Create `config.ru`

![create file](https://cloud.githubusercontent.com/assets/81055/2811901/e0d27758-ce37-11e3-8c0b-d7ebdd81ddf4.png)

```
```

We'll leave the file empty for a second and see what happens.

>
```
rackup
```

![missing run statement](https://cloud.githubusercontent.com/assets/81055/2811893/61c9f800-ce37-11e3-982a-bb6c33b14b0e.png)

**Missing run or map statement**

We've created the file, looks like rack needs to know the name of the file though.

#### Update `config.ru`

```
run IdeaBoxApp
```

Let's tell it that we want to run an app called **IdeaBoxApp**


>
```
rackup
```

![missing app.rb](https://cloud.githubusercontent.com/assets/81055/2811886/1d007514-ce37-11e3-9cb3-d428b8359de2.png)



**Create The File `app.rb`**

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

### Create the file  `Gemfile`

```
source 'https://rubygems.org'

gem 'sinatra', require: 'sinatra/base'
```

![Gemfile](https://cloud.githubusercontent.com/assets/81055/2811862/4111001a-ce35-11e3-8d97-5e270c70e672.png)

_don't forget to save your file_

### Download the gems

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

![rackup](https://cloud.githubusercontent.com/assets/81055/2811865/88f91cf0-ce35-11e3-9abf-8cd78c540de6.png)

Oh no, looks like rack doesn't know how to find `IdeaBoxApp`

```
unitialized constant IdeaBoxApp (NameError)
```

Let's tell rack 
