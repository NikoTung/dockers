FROM alpine:latest

LABEL maintainer "Niko <Nizh2008@gmail.com>"

ENV V2RAY_VERSION v3.6 

RUN apk upgrade --update \
    && apk add \
        bash \
        tzdata \
        curl \
        vim \
    && mkdir -p \ 
        /var/log/v2ray \
        /tmp/v2ray \
        /etc/v2ray/ \
       //usr/bin/v2ray/ \
    && curl -L -H "Cache-Control: no-cache" -o /tmp/v2ray/v2ray.zip \
        https://github.com/v2ray/v2ray-core/releases/download/${V2RAY_VERSION}/v2ray-linux-64.zip \
    && unzip /tmp/v2ray/v2ray.zip -d /tmp/v2ray/ \
    && cp /tmp/v2ray/v2ray-${V2RAY_VERSION}-linux-64/v2ray /usr/bin/v2ray/ \
    && cp /tmp/v2ray/v2ray-${V2RAY_VERSION}-linux-64/v2ctl /usr/bin/v2ray/ \
    && cp /tmp/v2ray/v2ray-${V2RAY_VERSION}-linux-64/geosite.dat /usr/bin/v2ray/ \
    && cp /tmp/v2ray/v2ray-${V2RAY_VERSION}-linux-64/geoip.dat /usr/bin/v2ray/ \
    && cp /tmp/v2ray/v2ray-${V2RAY_VERSION}-linux-64/vpoint_vmess_freedom.json /etc/v2ray/config.json \
    && chmod +x /usr/bin/v2ray/v2ray \
    && chmod +x /usr/bin/v2ray/v2ctl \  
    && apk del curl \
    && rm -rf /tmp/v2ray \
    && rm -rf /var/cache/apk/*
ENV PATH /usr/bin/v2ray:$PATH
CMD ["v2ray", "-config=/etc/v2ray/config.json"]
