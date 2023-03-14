FROM ruby:3.0.5-alpine

RUN apk update && apk add --no-cache build-base
EXPOSE 3456
EXPOSE 9292
EXPOSE 1234

# install dependencies for application
RUN apk -U add --no-cache \
bash \
python3 \
make \
gcc \
git \
curl \
nodejs \
npm \
yarn\
&& rm -rf /var/cache/apk/*

RUN gem install bundler
RUN gem install racc -v '1.6.2'
RUN chmod -R 777 /usr/local/bundle

RUN adduser -D -g '' dev
USER dev