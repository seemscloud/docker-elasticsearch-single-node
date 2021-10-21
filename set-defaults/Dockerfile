FROM alpine:3.13.1

COPY ./files/entrypoint.sh .

RUN apk add curl bash dos2unix && \
    dos2unix entrypoint.sh

CMD ["/bin/sh", "entrypoint.sh"]