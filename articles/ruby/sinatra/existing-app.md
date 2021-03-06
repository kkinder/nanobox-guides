# Existing Sinatra App
Part of what makes Nanobox so useful is you don't even need Ruby or Sinatra installed on your local machine to use them.

## Setup

#### cd into your Sinatra app
Change into an existing project folder:

```bash
cd your-sinatra-app
```

**HEADS UP**: All `nanobox` commands *must* be run from within your project folder.

#### Add a boxfile.yml
Nanobox uses a <a href="https://docs.nanobox.io/boxfile/" target="\_blank">boxfile.yml</a> to configure your app's environment.

At the root of your project create a `boxfile.yml` telling Nanobox you want to use the Ruby <a href="https://docs.nanobox.io/engines/" target="\_blank">engine</a>:

```yaml
run.config:
  engine: ruby
```

## Add a local DNS
Add a convenient way to access your app from the browser:

```bash
nanobox dns add local sinatra.dev
```

## Run the app
**HEADS UP**: If your app uses a database, you'll need to [add and configure it](/ruby/sinatra/add-a-database) before your app will run.

#### Classic Sinatra
To allow connections from the host machine into the app's container, you'll need to configure your app to listen on all available IP's (0.0.0.0):

```ruby
set :bind, "0.0.0.0"
```

```bash
nanobox run bundle exec ruby your-app.rb
```

#### Modular Sinatra
To allow connections from the host machine into the app's container, run the app so that it listens on all available IP's (0.0.0.0):

```bash
nanobox run rackup --host 0.0.0.0
```

#### Check it out
Visit your app at <a href="http://sinatra.dev:9292" target="\_blank">sinatra.dev:9292</a>

## Explore
With Nanobox, you have everything you need develop and run your Sinatra app:

```bash
# drop into a Nanobox console
nanobox run

# where ruby is installed,
ruby -v

# your gems are available,
bundle exec gem list

# and your code is mounted
ls

# exit the console
exit
```

## Now what?
Whats next? Think about what else your app might need and hopefully the topics below will help you get started with the next steps of your development!

* [Add a Database](/ruby/sinatra/add-a-database)
* [Frontend Javascript](/ruby/sinatra/frontend-javascript)
* [Local Environment Variables](/ruby/sinatra/local-evars)
* [Back to Sinatra overview](/ruby/sinatra)
