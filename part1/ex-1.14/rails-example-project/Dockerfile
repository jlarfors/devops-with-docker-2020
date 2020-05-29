FROM ruby:2.6.0-stretch

WORKDIR /work

COPY . .

EXPOSE 3000

RUN apt update \
    && apt install -y -qq --no-install-recommends \
    nodejs \
    && rm -rf /var/lib/apt/lists/*

RUN bundle install \
    && rails db:migrate

ENV RAILS_LOG_TO_STDOUT=true

ENTRYPOINT [ "rails" ]
CMD ["s"]

