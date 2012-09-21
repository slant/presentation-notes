# What Rails Can Do
James Edward Gray


## Models

rails g resource event article:belongs_to trigger
Event.group(:trigger).count

user = User.instantiate(id: 1, email: 'me@mail.com')
user.save!

t.column :search, "tsvector"
create index articles_search_index

Full-text search using postgresql
plainto_tsquery('english')

Hashes
hash.except(:key_i_dont_want_1, :key_i_dont_want_2)

rails g articles add_status_to_articles status
env.development?
- done by inquiry method
"magic".inquiry.magic?
can add your own by using method_missing


## Views

    % if current_user.try(:admin?)
      render "edit_links"
    % end


### Shorter version of erb

    config.action_view.erb_trim_mode = %

Render any object

    class Event < ActiveRecord::Base
      def to_partial_path
        "events/#{target}"
      end
    end

    render partial: 'thing', as: :mything

Build your own forms
inherit from ActiveView::Helpers::FormBuilder
Use method missing again

## Routes

Route Exception

    gem 'rescque', require: 'resque/server'

    module AdminValidator
      module_function

      def matches?(request)
        if (id = request.env['rack_admin'])

Streaming

all vs find_each
Use find_each not all, as all will put all records in memory up front,
find_each will grab each record, or group of records as required.

http://speakerdeck.com/u/jeg2

