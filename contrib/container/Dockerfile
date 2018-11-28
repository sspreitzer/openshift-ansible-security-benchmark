FROM rhel:7.4

RUN yum-config-manager --enable 'rhel-*-server-ansible-*-rpms'; \
    yum install -y \
    ansible \
    && \
    rm -rf /var/cache/yum 

ADD entrypoint /entrypoint
COPY ./bin/ /usr/libexec/s2i

LABEL io.s2i.scripts-url=image:///usr/libexec/s2i \
      io.openshift.s2i.scripts-url=image:///usr/libexec/s2i \
      io.openshift.s2i.destination=/tmp/src

USER 1001
WORKDIR /opt/app-root/src
ENTRYPOINT ["/entrypoint"]
CMD ["usage"]
