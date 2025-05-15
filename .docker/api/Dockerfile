FROM ntnp/laravel-dev:8.2
USER root

# Add imagick
RUN apt-get update; \
    apt-get install -y libmagickwand-dev libmagickcore-dev

RUN git clone https://github.com/Imagick/imagick.git --depth 1 /tmp/imagick; \
    cd /tmp/imagick; \
    git fetch origin master; git switch master; \
    phpize; \
    ./configure; \
    make; \
    make install; \
    docker-php-ext-enable imagick

# Add image optimizers
RUN apt-get install -y jpegoptim optipng pngquant

###

USER php
