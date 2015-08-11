# Add RSpec to a Nitrous Container with Sinatra

* Not set up yet? [Do this first](./README.md)

* In the ``sinatra-hello-world`` directory
* ``rspec --init``
* ``bundle``
* ``bundle exec rspec --init``
* Edit ``spec/spec_helper.rb``, add the following to the top of the file:
```
require_relative '../app.rb'
```
* ``bundle exec rspec``
* Should say:
```
No examples found.
Finished in 0.00034 seconds (files took 0.10197 seconds to load)
0 examples, 0 failures
```
* Edit ``spec/spec_helper``
Add the following to the top of the file:
```
ENV['RACK_ENV'] = 'test'

require 'rack/test'
require_relative '../app'

module RSpecMixin
  include Rack::Test::Methods
  def app() Sinatra::Application end
end
```
Add this to the ``configure`` block
```
  config.include RSpecMixin
```

* Add a new file ``spec/hello_spec.rb``
```require 'spec_helper'

describe 'Home Page' do
  it 'should be ok!' do
     get '/'
    expect(last_response).to be_ok
  end
end```

* ``bundle exec rspec``
* Should say:
```
Finished in 0.01605 seconds (files took 0.10791 seconds to load)
1 example, 0 failures
```
