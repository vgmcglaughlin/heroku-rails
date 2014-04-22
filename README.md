Test Heroku Deployment
============

Creating a sample rails app to show deploying a GitHub-hosted app to Heroku. This turned out to be really easy (the key being `git push heroku master`, same as any Heroku app), so this is all overkill. But it's done now, so here we go.

Steps
----------
(Misteps omitted)

Create repository in GitHub, pull down

    git clone https://github.com/vgmcglaughlin/heroku-rails.git
    cd heroku-rails/

Create rails app

    rails new .
    rails generate controller welcome

Add app/views/welcome/index.html.erb
Update config/routes.rb (not shown, see source)

Run locally, check at http://localhost:3000

    rails server

In Gemfile, replace gem 'sqlite3' with gem 'pg'

    bundle install

Log into Heroku, create new app

    heroku login
    heroku create

Check that remote was added

    git config -e

Commit everything

    git add .
    git commit -m "initial commit"

Push to GitHub

    git push origin master

Push to Heroku

    git push heroku master

Open Heroku deployed app (mine is at http://fast-temple-9343.herokuapp.com/)

    heroku open