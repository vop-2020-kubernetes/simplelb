FROM alpine:3.11

RUN apk add -U --no-cache iptables sudo

RUN addgroup simplelb && \
    adduser -G simplelb -H -s /sbin/nologin -D simplelb && \
    echo "simplelb ALL=(root) NOPASSWD: /sbin/iptables" > /etc/sudoers.d/simplelb

ADD entrypoint.sh /entrypoint.sh

USER simplelb

CMD ["/entrypoint.sh"]

