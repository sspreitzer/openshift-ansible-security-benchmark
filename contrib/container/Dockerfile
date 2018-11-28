FROM rhel:7.4

RUN yum-config-manager --enable 'rhel-*-server-ansible-*-rpms'; \
    yum install -y \
    ansible \
    && \
    rm -rf /var/cache/yum && \
    useradd -u 1001 -r -g 0 -d /opt/app-root/src -s /sbin/nologin \
      -c "Default Application User" default && \
    install -o 1001 -g 0 -d /opt/app-root

ADD entrypoint /entrypoint
COPY ./bin/ /usr/libexec/s2i

LABEL io.s2i.scripts-url=image:///usr/libexec/s2i \
      io.openshift.s2i.scripts-url=image:///usr/libexec/s2i

ENV ANSIBLE_INVENTORY=inventory \
    ANSIBLE_PLAYBOOKS=run.yml \
    ANSIBLE_REQUIREMENTS_YML=requirements.yml

USER 1001
WORKDIR /opt/app-root
ENTRYPOINT ["/entrypoint"]
CMD ["usage"]
