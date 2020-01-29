ARG flavor=latest

FROM phpmyadmin/phpmyadmin:$flavor

LABEL maintainer="tshinow@gmail.com"

RUN apt-get update \
  && apt-get install -y locales \
  && rm -rf /var/lib/apt/lists/* \
  && localedef -i ja_JP -f UTF-8 ja_JP.UTF-8
