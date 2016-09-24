FROM resin/rpi-raspbian:latest
MAINTAINER "Ajeet Singh Raina" <ajeetraina@gmail.com>

RUN apt-get update && apt-get install -qy curl ca-certificates
WORKDIR /root/
RUN mkdir /root/prometheus

RUN curl -sSLO https://s3-eu-west-1.amazonaws.com/downloads.robustperception.io/prometheus/prometheus-linux-arm-nightly.tar.gz && \
   tar -xvf prometheus-linux-arm-nightly.tar.gz -C /root/prometheus/ --strip-components=1 && \
   rm prometheus-linux-arm-nightly.tar.gz

workdir /root/prometheus

RUN mkdir -p /usr/share/prometheus
RUN mkdir -p /etc/prometheus
RUN mv ./prometheus /usr/bin/
RUN mv ./promtool /usr/bin/
RUN mv ./console_libraries /usr/share/prometheus/
RUN mv ./consoles /usr/share/prometheus/

RUN ln -s /usr/share/prometheus/console_libraries /etc/prometheus/

EXPOSE 9090
VOLUME [ "/prometheus" ]
WORKDIR /prometheus
ENTRYPOINT [ "/usr/bin/prometheus" ]
CMD ["-config.file=/etc/prometheus/prometheus.yml", \
     "-storage.local.path=/prometheus", \
     "-web.console.libraries=/usr/share/prometheus/console_libraries", \
     "-web.console.templates=/usr/share/prometheus/consoles" ]
