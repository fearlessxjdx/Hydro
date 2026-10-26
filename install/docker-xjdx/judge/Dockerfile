FROM node:24

COPY ./entrypoint.sh /root/entrypoint.sh

RUN apt-get -qq update && \
    apt-get install -y \
    gcc \
    python3 \
    g++ && \
    chmod +x /root/entrypoint.sh && \
    # node is at /usr/local/bin but hydrojudge will find it at /usr/bin
    # so make a symlink to it
    ln -s /usr/local/bin/node /usr/bin/node

RUN yarn global add pm2 @hydrooj/hydrojudge && \
    wget https://github.com/criyle/go-judge/releases/download/v1.13.3/go-judge_1.13.3_linux_amd64v3 -O /usr/bin/sandbox && \
    chmod +x /usr/bin/sandbox

ENTRYPOINT ["/root/entrypoint.sh"]
