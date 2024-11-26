---
title: "How to use Procfile for Ruby on Rails apps"
meta_title: ""
date: 2024-07-13T05:00:00Z
description: "Understanding the value of using the Procfile in the Rails apps."
image: "/images/bck.jpg"
categories: ["Application", "Ruby on Rails", "How to"]
tags: ["ruby-on-rails","active-record","developer","database","back-end"]
author: "Lee Sheppard"
draft: false
---
A Procfile is a text file used in Ruby on Rails applications to define the various processes that make up the application. Each line in the Procfile specifies a process type and the command used to run that process. Procfiles are commonly used with process management tools like Foreman, which can read the Procfile and start the specified processes. There are many hosting services that now utilise this type of file to operate your applications with.

Here's an example of how to write a Procfile correctly for a Ruby on Rails application:

```ruby
web: bundle exec rails server -p 3000
worker: bundle exec rake jobs:work
```

Let's break down each part of this Procfile:

1. `web`: This line specifies the process type, in this case, it's the web server process. When you run this line through a process management tool, it will start the web server for your Rails application.

2. `bundle exec rails server`: This is the command to run the web server process. It uses the `bundle exec` prefix to ensure that the Rails server is executed within the context of the application's dependencies managed by Bundler.

3. `worker`: This line specifies another process type, in this case, it's a worker process. Worker processes are often used for background jobs, and this line tells the process management tool to start the worker process.

4. `bundle exec rake jobs:work`: This is the command to run the worker process. It uses the `bundle exec` prefix just like the web server command to ensure that the worker process is executed within the application's context.

When you have a Procfile set up with these lines, you can use process management tools like Foreman to start all the processes defined in the Procfile with a single command. This can be especially useful in development environments to mimic the environment in which the application will run in production.

The names of each process (e.g. web, worker) can be customised to suit your preferences, these titles are seen in your terminal output and as such are used to identify what processes are running or have failed. 

Further, you can have a Procfile.dev in your application to run processes specific to local development environments. A new Rails application (version 7) with initial configuration set up to use Yarn/ESBuild/TailwindCSS would typically have a Procfile.dev that looks like this:

```ruby
web: bin/rails server -p 3000
js: yarn build --watch
css: yarn build:css --watch
```

A separate script would be required to run this Procfile locally of which you can place in the **bin** folder. The standard practice is to have a script named **dev** in this folder which would contain the following:

```sh
#!/usr/bin/env sh

if ! gem list foreman -i --silent; then
  echo "Installing foreman..."
  gem install foreman
fi

exec foreman start -f Procfile.dev "$@"
```

Now when you run the **bin/dev** from the command line your processes will all start up using Foreman.

An alternative configuration for Rails developers is to optimise the operation of their apps using the Puma server. You can use the config file by using this line in the Procfile for reference:

```ruby
web: bundle exec puma -C ./config/puma.rb
```

In summary, a Procfile in Ruby on Rails is a simple yet powerful way to manage multiple processes within your application. It allows you to define process types and their respective commands, making it easier to start and manage different parts of your application.