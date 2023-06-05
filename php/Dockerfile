# na bazie obrazu php z fpm
FROM php:fpm-alpine

# aktualizacja systemu i instalacja pakietu curl
RUN apk update && apk add --no-cache \
    curl \
    && rm -rf /var/cache/apk/*

# wypuszczenie portu 9000
EXPOSE 9000

# sprawdzanie stanu zdrowia kontenera
HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 \
    CMD [ "curl localhost:9000" ]

# uruchomienie php-fpm
CMD [ "php-fpm" ]
