FROM fluent/fluentd:v1.16-1

USER root

RUN gem install fluent-plugin-elasticsearch --no-document

COPY fluent.conf /etc/fluentd/fluent.conf

USER fluent

ENTRYPOINT ["fluentd"]
CMD ["-c", "/etc/fluentd/fluent.conf", "-v"]

