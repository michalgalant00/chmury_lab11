# na bazie obrazu nginx w wersji 1.21.1-alpine
FROM nginx:1.21.1-alpine

# ustawienie katalogu roboczego
WORKDIR /var/www/html/

# aktualizacja systemu i instalacja curl
RUN apk add --no-cache \
    curl \
    && rm -rf /var/cache/apk/*

# skopiowanie konfiguracji serwera do kontenera
COPY default.conf /etc/nginx/conf.d/

# wypuszczenie portu 6666
EXPOSE 6666

# sprawdzanie stanu zdrowia kontenera
HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 \
    CMD [ "curl localhost:6666" ]

# uruchomienie serwera nginx
CMD [ "nginx", "-g", "daemon off;" ]