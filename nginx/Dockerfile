FROM base:v1
LABEL name="liuxsen" email="wyliuxsen@163.com"

# RUN apt-get update && \
#     apt-get install libpcre3 libpcre3-dev  zlib1g-dev  openssl
COPY nginx-1.16.0.tar.gz /usr/local/src/
WORKDIR /usr/local/src/
RUN tar -xvf nginx-1.16.0.tar.gz
RUN ls 
WORKDIR /usr/local/src/nginx-1.16.0
RUN pwd
RUN ls
RUN  ./configure \
    --prefix=/usr \
    --sbin-path=/usr/sbin/nginx \
    --conf-path=/etc/nginx/nginx.conf \
    --error-log-path=/var/log/nginx/error.log \
    --http-log-path=/var/log/nginx/access.log \
    --pid-path=/var/run/nginx/nginx.pid  \
    --lock-path=/var/lock/nginx.lock \
    --user=root \
    --group=root \
    # --with-http_ssl_module \
    # --with-http_flv_module \
    # --with-http_stub_status_module \
    # --with-http_gzip_static_module \
    --with-pcre 
RUN make && make install

EXPOSE 80

# https://www.yuque.com/buntwl/nbgz9l/vexf2a
CMD [ "/usr/sbin/nginx", "-g", "daemon off;"]


