ARG flavor=7

FROM centos:$flavor

LABEL maintainer="tshinow@gmail.com"

ENV CURRENT_DIR /var/www/laravel

RUN yum update -y \
  && yum install -y \
    git \
    zip \
    unzip \
    https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm \
    http://rpms.remirepo.net/enterprise/remi-release-7.rpm \
  && yum --enablerepo=remi-php74 install -y \
    php \
    php-bcmath \
    php-mbstring \
    php-pdo \
    php-xml \
  && yum clean all \
  && rm -rf /var/cache/yum/* \
  && mkdir -p $CURRENT_DIR

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

EXPOSE 8000

WORKDIR $CURRENT_DIR
