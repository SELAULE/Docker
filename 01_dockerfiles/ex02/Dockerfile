FROM ruby:2.3

RUN apt-get update && apt-get install -y --no-install-recommends

WORKDIR /opt/app
COPY Gemfile* ./
RUN bundle install
COPY . .

EXPOSE 3000
CMD ["rails", "server", "-b", "-p", "0.0.0.0"]