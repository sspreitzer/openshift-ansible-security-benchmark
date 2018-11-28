FROM centos:7.5

RUN yum-config-manager --enable 'rhel-*-server-ansible-*-rpms'; \
    yum-config yum install -y \
    ansible \
    git \
    && \
    rm -rf /var/cache/yum && \
    git clone -b 3.9 https://github.com/sspreitzer/openshift-ansible-security-benchmark.git /opt/openshift-ansible-security-benchmark
