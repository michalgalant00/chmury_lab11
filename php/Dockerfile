# na bazie obrazu php z fpm
FROM php:fpm-alpine

# aktualizacja systemu i instalacja pakietu curl
RUN apk update && apk add --no-cache \
    curl \
    && rm -rf /var/cache/apk/*

# wypuszczenie portu 9000
EXPOSE 9000

# uruchomienie php-fpm
CMD [ "php-fpm" ]
