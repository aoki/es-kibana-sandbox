FROM openjdk:8-jre-alpine

RUN wget -q https://dl.embulk.org/embulk-latest.jar -O /bin/embulk \
  && chmod +x /bin/embulk

RUN apk add --no-cache libc6-compat \
  && embulk gem install embulk-parser-ltsv \
  && embulk gem install embulk-output-elasticsearch \
  && embulk gem install embulk-filter-query_string

WORKDIR /work
ENTRYPOINT ["java", "-jar", "/bin/embulk"]
