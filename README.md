# Campfire

Rails action cable chat application (from guide: https://www.youtube.com/watch?v=n0WUjGkDFS0)


## Models
### Message
- content: text

## Controllers
### RoomsController
- show

## Channels
### room_channel
- subscribed - stream_from "room_channel"
- speak(data)

## Jobs
### MessageBroadcastJob
- perform(message)


## Issues Encountered

1. Needed to add this in application.html.erb
```ruby
<%= action_cable_meta_tag %>
```

2. Needed to add JQuery-rails gem in Gemfile
```ruby
gem 'jquery-rails'
```

3. Needed to update application.js to add Jquery
```ruby
//= require jquery
//= require jquery_ujs
```

