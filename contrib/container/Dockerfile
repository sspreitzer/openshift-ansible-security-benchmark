FROM centos:7.5

RUN yum install -y \
    ansible \
    git \
    && \
    rm -rf /var/cache/yum && \
    git clone -b 3.9 https://github.com/sspreitzer/openshift-ansible-security-benchmark.git /opt/openshift-ansible-security-benchmark