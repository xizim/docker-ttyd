FROM ubuntu:12.04
LABEL maintainer "xiz - orz@xiz.im"
COPY ttyd /usr/bin
WORKDIR /
RUN chmod u+x /usr/bin/ttyd
EXPOSE 7681
ENTRYPOINT ["ttyd"]
CMD ["bash"]
