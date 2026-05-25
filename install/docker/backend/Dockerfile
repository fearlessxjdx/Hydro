FROM node:22

COPY ./entrypoint.sh /root/entrypoint.sh

RUN yarn global add pm2 hydrooj @hydrooj/ui-default @hydrooj/geoip
RUN cd '/usr/local/share/.config/yarn/global/node_modules/@hydrooj/geoip/' && \
    wget https://cdn.jsdelivr.net/npm/geolite2-city/GeoLite2-City.mmdb.gz && \
    gzip -d GeoLite2-City.mmdb.gz && \
    chmod +x /root/entrypoint.sh

ENTRYPOINT ["/root/entrypoint.sh"]
