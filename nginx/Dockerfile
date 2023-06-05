FROM nginx:1.21.1-alpine

WORKDIR /var/www/html/

RUN apk add --no-cache \
    curl \
    && rm -rf /var/cache/apk/*

COPY nginx.conf /etc/nginx/conf.d/

EXPOSE 6666

HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 \
    CMD [ "curl localhost:6666" ]

CMD ["nginx", "-g", "daemon off;"]