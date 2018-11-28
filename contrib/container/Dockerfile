FROM centos:7.5

RUN yum install -y
    ansible \
    git \
    && \
    rm -rf /var/cache/yum && \
    { cd /opt; git clone https://github.com/sspreitzer/openshift-ansible-security-benchmark.git && git checkout 3.9 }

