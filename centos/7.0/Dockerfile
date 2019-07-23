FROM centos:7.0.1406
LABEL maintainer "xiz - orz@xiz.im"
#RUN yum update -y
COPY ttyd /usr/bin
WORKDIR /
RUN chmod u+x /usr/bin/ttyd
EXPOSE 7681
ENTRYPOINT ["ttyd"]
CMD ["bash"]
