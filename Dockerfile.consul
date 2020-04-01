FROM alpine
RUN apk add git bash curl
RUN git clone https://github.com/Devlin556/consul-heroku-buildpack.git
RUN sed -i s/\-u/\-e/g /consul-heroku-buildpack/bin/compile
RUN /consul-heroku-buildpack/bin/compile /usr/local/bin

#FROM scratch
#COPY --from=0 /usr/local/bin/consul /usr/local/bin/
CMD consul agent -dev -data-dir /tmp/consul -client 0.0.0.0 -http-port ${PORT}
#CMD consul agent -server -bootstrap-expect 1 -data-dir /tmp/consul -client 0.0.0.0 -http-port ${PORT}
