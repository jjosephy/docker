FROM debian

RUN \
    apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927 && \
    echo "deb http://repo.mongodb.org/apt/debian wheezy/mongodb-org/3.2 main" | tee /etc/apt/sources.list.d/mongodb-org-3.2.list && \
    apt-get update && \
    apt-get install -y mongodb-org && \
    mkdir -p /data/db && \
    chown mongodb /data/db && \
    echo "#!/bin/sh\nexit 0" > /usr/sbin/policy-rc.d

    #&& \
    #rm -rf /var/lib/apt/lists/*

EXPOSE 27017
ENTRYPOINT ["/usr/bin/mongod"]
