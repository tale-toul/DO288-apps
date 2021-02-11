# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent
LABEL io.openshift.expose-service="8080:http" \
      io.k8s.description="This is the apache client container" \
      io.k8s.display-name="Winter of our discontent" \
      io.k8s.tags="apache, httpd"
EXPOSE 8080
RUN sed -ri -e "s/Listen 80/Listen 8080/" /etc/httpd/conf/httpd.conf 
RUN    chgrp -R 0 /var/log/httpd /var/run/httpd && \
       chmod -R g=u /var/log/httpd /var/run/httpd 
USER 1001

