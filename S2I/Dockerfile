#
FROM openshift/base-centos7

# Maintainer name in the image metadata
MAINTAINER Guillaume Martinez <guillaume.lunik@gmail.com>


# Set labels used in OpenShift to describe the builder image
LABEL io.k8s.description="Platform for building html web application"
LABEL io.k8s.display-name="builder 1.0.0"
LABEL io.openshift.expose-services="8080:http"
LABEL io.openshift.tags="builder,1.0.0,nginx"
LABEL io.openshift.s2i.scripts-url="image:///tmp/s2i-scripts/"

# Install required packages here:
RUN yum install -y --setopt=tsflags=nodocs nginx
RUN rpm -V nginx
RUN yum clean all -y

COPY ./.s2i/bin/ /tmp/s2i-scripts/

# Set NGINXPATH env
ENV NGINXPATH /usr/share/nginx/html

# Set the default port for applications built using this image
EXPOSE 8080
