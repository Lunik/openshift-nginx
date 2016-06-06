#
FROM nginx

# Maintainer name in the image metadata
MAINTAINER Guillaume Martinez <guillaume.lunik@gmail.com>


# Set labels used in OpenShift to describe the builder image
LABEL io.k8s.description="Platform for building html web application"
LABEL io.k8s.display-name="builder 1.0.0"
LABEL io.openshift.expose-services="8080:http"
LABEL io.openshift.tags="builder,1.0.0,nginx"
LABEL io.openshift.s2i.scripts-url="/tmp/s2i-scripts/"

# Install required packages here:
# RUN yum install -y ... && yum clean all -y

COPY ./.s2i/bin/ /tmp/s2i-scripts/
ENV PATH /tmp/s2i-scripts/:$PATH

# Set NGINXPATH env
ENV NGINXPATH /usr/local/nginx/html

# Set the default port for applications built using this image
EXPOSE 8080
