# API Response Cache
Improve rails server api response time by caching your rails api response response data to client side.

## Installation
Add to Gemfile
```
gem 'api-response-cache'
```
Then run
```
bundle install
```

## Configuration
If you want to change config create file at ```config/initializers/api_response_cache.rb```
```
ApiResponseCache.configure do |config|
  config.refresh_by_request_params = false  # true to saperate cache by request params
  config.cache_by_headers = ['header-key']  # optional this need when saperate cache with header only
end
```

## Basic Usage
```
class ExamplesController < ActionController::API
  cache_response_for :index

  def index
    # ... your code here
  end
end
```
#### Add expire duration
```
cache_response_for :index, expires_in: 1.day
```

#### Clear Cache
```
ApiResponseCache.clear
```



## TO DO
- [ ] Block check in contoller
- [ ] Block check in config
