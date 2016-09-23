
How to build this Image


pi@raspberrypi:~/ajeetraina-promo/prometheus $ sudo docker build -t ajeetraina/prometheus-armh7 .
Sending build context to Docker daemon 38.24 MB
Step 1 : FROM armbuild/debian
 ---> e9bcf72ae729
Step 2 : MAINTAINER "Ajeet Singh Raina" <ajeetraina@gmail.com>
 ---> Using cache
 ---> 11b8679a8d5c
Step 3 : RUN mkdir -p /usr/share/prometheus
 ---> Using cache
 ---> 7fa309215658
Step 4 : RUN mkdir -p /etc/prometheus
 ---> Running in 2af07c9db599
 ---> 94812db69c0e
Removing intermediate container 2af07c9db599
Step 5 : COPY prometheus /bin/prometheus
 ---> 2d96afcecbfe
Removing intermediate container cccca8fc4f0b
Step 6 : COPY promtool /bin/promtool
 ---> c5cc25eb5bf9
Removing intermediate container d7127ed1c738
Step 7 : COPY console_libraries/ /usr/share/prometheus/console_libraries/
 ---> 39892edbb891
Removing intermediate container f1afed03c63c
Step 8 : COPY consoles/ /usr/share/prometheus/consoles/
 ---> f3ea7107a312
Removing intermediate container a11651587ced
Step 9 : RUN ln -s /usr/share/prometheus/console_libraries /etc/prometheus/
 ---> Running in 7df4665e99e7
 ---> a852aef97e35
Removing intermediate container 7df4665e99e7
Step 10 : EXPOSE 9090
 ---> Running in b7c7c289702e
 ---> 8a5bec400745
Removing intermediate container b7c7c289702e
Step 11 : VOLUME /prometheus
 ---> Running in f62d9a1ea743
 ---> 519f33a7360e
Removing intermediate container f62d9a1ea743
Step 12 : WORKDIR /prometheus
 ---> Running in 96010ea43ab3
 ---> 8e9027385551
Removing intermediate container 96010ea43ab3
Step 13 : ENTRYPOINT /bin/prometheus
 ---> Running in 8ab5e125de5e
 ---> 019fe0c11545
Removing intermediate container 8ab5e125de5e
Step 14 : CMD -config.file=/etc/prometheus/prometheus.yml -storage.local.path=/prometheus -web.console.libraries=/usr/share/prometheus/console_libraries -web.console.templates=/usr/share/prometheus/consoles
 ---> Running in 8cfcc9d3216c
 ---> a2193c756fd5
Removing intermediate container 8cfcc9d3216c
Successfully built a2193c756fd5
pi@raspberrypi:~/ajeetraina-promo/prometheus $


