FROM ruby:2.5.5

RUN apt-get update -y
RUN apt-get install -y rails

ONBUILD WORKDIR /opt
ONBUILD	RUN		rails new app
ONBUILD WORKDIR app
ONBUILD	RUN		bundle update
ONBUILD	RUN		rails db:migrate
ONBUILD	RUN		rails db:seed
ONBUILD	EXPOSE	3000

# how to run it
# docker build -t ft-rails:on-build .
