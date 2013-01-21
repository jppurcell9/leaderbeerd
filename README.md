leaderbeerd
===========
Description
---
Leaderbeerd is a web application for comparing and aggregating checkin data from the Untappd API.  
This is currently for my amusement only.

Building
----
Install RVM - https://rvm.io/rvm/install/

    \curl -L https://get.rvm.io | bash -s stable --ruby

Install Ruby 1.9.3

    rvm install 1.9.3

Install bundler

    gem install bundler

Install gems

    bundle install

Running
-----
###Start the Sinatra server

    bundle exec thor leaderbeerd:app:server --untappd_client_id=$LEADERBEERD_UNTAPPD_CLIENT_ID --untappd_secret=$LEADERBEERD_UNTAPPD_SECRET --untappd_access_token=$LEADERBEERD_UNTAPPD_ACCESS_TOKEN --untappd_usernames=[usernames] --aws_key=$LEADERBEERD_AWS_ACCESS_KEY_ID --aws_secret=$LEADERBEERD_AWS_SECRET_ACCESS_KEY --log_level=debug -f -d --pid_file=tmp/server.pid

###Start the Untappd consumer

    bundle exec thor leaderbeerd:app:process --untappd_client_id=$LEADERBEERD_UNTAPPD_CLIENT_ID --untappd_secret=$LEADERBEERD_UNTAPPD_SECRET --untappd_access_token=$LEADERBEERD_UNTAPPD_ACCESS_TOKEN --untappd_usernames=[usernames] --aws_key=$LEADERBEERD_AWS_ACCESS_KEY_ID --aws_secret=$LEADERBEERD_AWS_SECRET_ACCESS_KEY --log_level=debug
