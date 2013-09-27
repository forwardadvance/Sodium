# Sodium

A super clean DLS for defining blogs and websites, no database required. Works with any Ruby framework but plays especially nicely with Sinatra.

Define your site using calls like blog_post :post_title. Write your content in HAML, Markdown, ERB, whatever suits you. Place it in your views directory and you're ready to roll!

## No database

I blog on the train. I have no network access, so no access to a remote CMS. I wanted to be able to write my blog posts in HAML, and store them in a Git repository.

I wrote Sodium to help me do that.

## Sinatra

Sodium will work with any Ruby framework from Camping to Rails, but plays especially well with Sinatra. If you'd like to use Sinatra, check out the sodium_sinatra gem instead. (note: not yet available)

## Heroku

Sodium is fully compatible with Heroku. Get your blog live in minutes on Heroku free tier.

## Installation

Add this line to your application's Gemfile:

    gem 'sodium'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install sodium

## Usage

Define your website like so

    @website = Website.new do
      add_blog :my_blog do
        add_post :rule_world
          self.title = "How to Rule the World with Ruby"
        end
        add_post :build_awesome
          self.title = "How to build more awesome"
        end
      end
    end

You'll get back an object of class Website which you can then query like so:

    # Get the default blog
    @blog = @website.blog

    # Get a blog by key if you have more than one
    @website.blog[:by_blog]

    # Get the posts for a blog
    @website.blog.posts

    # Get the first blog post
    @website.blog.first_post


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
