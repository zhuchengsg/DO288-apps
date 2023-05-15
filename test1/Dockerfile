FROM registry.access.redhat.com/ubi7/ubi

RUN yum update --disableplugin=subscription-manager -y && rm -rf /var/cache/yum && \
    yum install --disableplugin=subscription-manager httpd -y && rm -rf /var/cache/yum && \
	echo "The Web Server is Running" > /var/www/html/index.html

# RUN touch /run/nginx.pid \
#  && chgrp -R 0 /var/log/nginx /run/nginx.pid \
#  && chmod -R g+rwx /var/log/nginx /run/nginx.pid

EXPOSE 80
USER httpd

# Start the service
CMD ["-D", "FOREGROUND"]
ENTRYPOINT ["/usr/sbin/httpd"]


