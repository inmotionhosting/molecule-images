FROM centos:7

RUN yum update -y && \
    yum install -y \
        hostname \
        openssh \
        openssh-server \
        python3 \
        python3-pip \
        sudo \
        which && \
    yum autoremove -y && \
    yum clean all && \
    rm -rf \
        /lib/systemd/system/{*getty*,systemd*udev*} && \
    cp /bin/true /usr/sbin/agetty && \
    echo "Defaults !requiretty" >> /etc/sudoers

VOLUME ["/sys/fs/cgroup"]
CMD ["/usr/lib/systemd/systemd"]
