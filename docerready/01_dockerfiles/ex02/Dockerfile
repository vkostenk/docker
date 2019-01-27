FROM ruby:latest

RUN apt-get update -y
RUN apt-get upgrade -y
RUN gem install rails

# ONBUILD command as an instruction the parent Dockerfile
# gives to the child Dockerfile

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# Rake is Ruby Make, a standalone Ruby utility that replaces the Unix utility
# ‘make’, and uses a ‘Rakefile’ and .rake files to build up a list of tasks.

# db:migrate runs migrations for the current env that have not run yet (Migrate the database)
# db:seed  loads the data from db/seeds.rb into the database.
# This is generally used for development and production databases.
# It's permanent data that you use to start an empty application


# to test it
# docker build -t ft-rails:on-build .
# docker build -t ex02 .
# docker run -it --rm -p 3000:3000 ex02
