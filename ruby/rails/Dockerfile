FROM ruby:3.3-alpine

RUN apk add --no-cache build-base postgresql-dev nodejs yarn

WORKDIR /app
COPY Gemfile Gemfile.lock ./
RUN bundle install

COPY . .

EXPOSE 3000
CMD ["bundle","exec","puma","-C","config/puma.rb"]
