# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

LABEL io.k8s.description="HTTP server child" \
      io.k8s.display-name="HTTP web server" \
      io.openshift.tags="web,httpd, apache" \
      io.openshift.expose-service="8080:http"

RUN sed -i -e 's/Listen 80/Listen 8080/' /etc/httpd/conf/httpd.conf && \
    chown -R 1001:0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd

EXPOSE 8080

USER 1001

CMD /usr/sbin/httpd -DFOREGROUND
