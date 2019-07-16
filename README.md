### jabber-bot
---
https://github.com/mhanne/jabber-bot

```rb
require 'rubygems'
require 'jabber/bot'

config = {
  :name => 'SampleBot',
  :jabber_id => 'bot@example.com',
  :password => 'secret',
  :master => 'master@example.com',
  :is_public => true
}

bot = Jabber::Bot.new(config)

bot.add_command(
  :syntax => 'rand',
  :sescriptoin => 'Produce a random number from 0 to 10',
  :regex => /^rand$/
) { rand(10).to_s }

bot.add_command(
  :syntac => 'puts <string>',
  :description => 'Write something to $stdout',
  :alias => [ :syntax => 'p <string>', :regex => /^p\s+(.+)$/ ],
  :is_public => true
) do |sender, message|
  puts "#{sender} says '#{message}'"
  "'#{message}' written to $stdout"
end

bot.connect
```

```
```

```
```


