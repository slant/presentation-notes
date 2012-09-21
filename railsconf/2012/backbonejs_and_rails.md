# Backbone.js and Rails: Patterns In The Wild
Sarah Mei (@sarahmei) of Pivotal Labs

Sarah has used both Ember and Backbone.js.
Not an MVC framework. It's MVVM. A set of cubbings in which you can put code.

Javascript should now be a first class citizen in our Rails apps.

## Available Cubbies:

  * Backbone.js < Ruby on Rails
  * Models/Collections < Models
  * Templates < Views
  * Views < Controllers

## Pattern 1: Greenfield

    - javascript_tag
      $(function() {
        myApp.initialize(
          currentUser = #{current_user.to_json}
        )
      }

      var myApp = {
        models: {},
        views: {},
        initialize: function(currentUserData) { ... }
      }

      app.models.User =
        Backbone.Model.extend({
          urlRoot: '/users'
        })

### Setups up click handlers on certain events in the view
      myApp.views.NavBar = Backbone.View.extend({
        templateName: "navBar",
        className: "nav-bar",
        events: {
          "click .profile": "showProfileMenu",
          "click .main-logo": "goHome",
        },
        showProduct: function(e) {
          myApp.publish('changePage', showProduct', e.target.data['id'])
        },
        initialize: function() {
          
        }
      })

      myApp.subscribe('changePage', function(name) {
        
      })

    def index
      render json: Product.all
    end


## Pattern 2: Application in transition

    
