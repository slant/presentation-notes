# Wrangling Large Rails Codebases

## Stephan Hagemann

  - [Twitter](http://twitter.com/shageman)
  - [Github](http://github.com/shageman)
  - [Profile at pivotallabs.com](http://pivotallabs.com/users/shagemann/profile)

## Rails Engines

### Mounting

    # routes.rb
    MyApp::Application.routes.draw do
      mount MyEngine::Engine => "/engine"
    end

## Gems and Engines

  In your next Rails app:

  - namespace everything
  - Do nothing in the Rails app, but give yourself an engine.

