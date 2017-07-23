# blog

This repository contains the server that powers my blog, as well as all the posts. I can't promise I'll blog often or be remotely interesting, but if you find it somewhat interesting that's fine with me!

## Posts

So all the posts are stored in the `posts` directory and are markdown files.  
These are parsed at runtime with the [marked](https://npm.im/marked) library and have a browser cache time of 1 day by default. This can be overridden using the environment variable `CACHE_HOURS`.  
Meta data about posts are in the `posts/meta` directory and are JSON files, these should have at least the following attributes:

- `title` The title of the post
- `date` The date of the post (in ISO format)
- `author` The name of the person who wrote this post


## Backend

The actual server is written in node.js running a simple [express](https://npm.im/express) app, which in my setup is fronted by [Varnish](http://varnish-cache.org) for caching and then [CloudFlare](https://cloudflae.com) for global distribution.


## Analytics

For analytics I decided to just use Google Analytics, I didn't think it was worth introducing any other complexity or dependencies for now.
