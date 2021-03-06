# Sinatra on Nitrous.io

# Steps to set up Sinatra on Nitrous.io
* Register for Nitrous
* Confirm email address
* Link with GitHub (not yet necessary)
* Create new Workspace called ``stujo1``
* Create new Container based on ``Ruby on Rails`` template
* Open IDE
* ``cd ~/code`` - Change to code directory
* Optional: ``rm -rf example`` - Remove Rails Example Code
* ``mkdir sinatra-hello-world``
* ``cd sinatra-hello-world``
* ``bundle init``
* edit ``Gemfile``
```
source "https://rubygems.org"

gem "sinatra"
```
* ``bundle``
* add ``./app.rb`` - this will be our app
```
require 'sinatra'

configure :development do   
  set :port, 3000
  set :bind, '0.0.0.0'   
end

get '/' do
  'Hello World!'
end
```
* ``bundle exec ruby ./app.rb`` - Run the sinatra app
* Wait for server to start
* In the IDE select ``Preview`` -> ``Port 3000(Default)``
* A new browser tab/window should open with 'Hello World!'

# Next Step
* [Add RSpec](add-rspec.md)
* [Add GitHub Support](add-github.md)

# Resources
* [Nitrous Community Tutorials](https://community.nitrous.io/)
