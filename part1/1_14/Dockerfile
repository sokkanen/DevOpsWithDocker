FROM ruby:2.6.0
EXPOSE 3000

COPY ./rails-example-project /usr/fourteen
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
WORKDIR /usr/fourteen
RUN bundle install
RUN rails db:migrate
CMD rails s
