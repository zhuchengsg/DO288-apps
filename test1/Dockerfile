FROM registry.access.redhat.com/ubi7/ubi

RUN yum update --disableplugin=subscription-manager -y && rm -rf /var/cache/yum && \
    yum install --disableplugin=subscription-manager httpd -y && rm -rf /var/cache/yum

RUN	echo "The Web Server is Running" > /var/www/html/index.html

#	touch /run/httpd/httpd.pid & \
#	chgrp -R 0 /run/httpd/httpd.pid && \
#       chmod -R g=u /run/httpd/httpd.pid


EXPOSE 80
USER root

# Start the service
CMD ["-D", "FOREGROUND"]
ENTRYPOINT ["/usr/sbin/httpd"]

