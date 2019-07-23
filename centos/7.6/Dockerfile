FROM centos/systemd
LABEL maintainer "xiz - orz@xiz.im"
RUN yum update -y \
yum -y install epel-release vim
COPY ttyd /usr/bin
WORKDIR /
RUN chmod u+x /usr/bin/ttyd
EXPOSE 7681
#CMD ["/usr/sbin/init"]
ENTRYPOINT ["ttyd"]
#CMD /usr/sbin/init && /usr/bin/ttyd bash
CMD ["bash"]
