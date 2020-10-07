FROM jessestuart/caddy-cloudflare:v0.11.0

RUN mkdir /srv/www /srv/www/ssl
COPY index.html /srv/www/index.html
COPY vir.canbao.cf.crt /srv/www/ssl/vir.canbao.cf.crt
COPY vir.canbao.cf.key /srv/www/ssl/vir.canbao.cf.key
EXPOSE 80 443 2015
VOLUME /root/.caddy /srv
WORKDIR /srv

ENTRYPOINT ["/bin/parent", "caddy"]
CMD ["--conf", "/etc/Caddyfile", "--log", "stdout", "--agree=$ACME_AGREE"]
