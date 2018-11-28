FROM rhel:latest

ENV GITREPO="https://github.com/sspreitzer/openshift-ansible-security-benchmark.git" \
    GITREF="3.9"

RUN yum-config-manager --enable 'rhel-*-server-ansible-*-rpms'; \
    yum install -y \
    ansible \
    git \
    && \
    rm -rf /var/cache/yum && \
    git clone -b ${GITREF} ${GITREPO} /opt/openshift-ansible-security-benchmark
