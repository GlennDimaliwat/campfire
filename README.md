# Campfire

Rails action cable chat application

## Project steps
1. Created project
```
rails new campfire
```

2. Created rooms controller
```
rails g controller rooms show
```

3. Modified rooms controller's show method

4. Created Message model
```
rails g model Message content:text
rails db:migrate
```

5. Created a dummy message in `rails c`
```
Message.create! content: 'Hello World'
```

6. Created a room channel
```
rails g channel room speak
```

7. Modified `room_channel.rb`

8. Modified `room.coffee`

9. Added items in `issues encountered`  (**[see below](#Issues)**)

10. `bundle install` and restart server

11. Created a job MessageBroadcast
```
rails g job MessageBroadcast
```
12. Modified `message_broadcast_job.rb`


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


## <a id="Issues"></a> Issues Encountered

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

## References

David Heinemeier Hansson:
https://www.youtube.com/watch?v=n0WUjGkDFS0

Kaizeras:
https://github.com/Kaizeras/actioncable-chat-tutorial