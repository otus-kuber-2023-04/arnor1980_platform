FROM busybox:1.35

RUN addgroup -g 1001 web
RUN adduser -G web -u 1001 web -D

USER web

WORKDIR /app

COPY ./hello.html /app

EXPOSE 8000

CMD ["busybox", "httpd", "-f", "-v", "-p", "8000", "-h", "/app"]
