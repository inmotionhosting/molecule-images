FROM centos:8 AS base
RUN dnf install -y hostname openssh openssh-server python3 sudo which && \
    dnf autoremove -y && \
    dnf clean all
RUN rm -rf /lib/systemd/system/{*getty*,systemd*udev*} && \
    cp /bin/true /usr/sbin/agetty && \
    echo "Defaults !requiretty" >> /etc/sudoers
VOLUME ["/sys/fs/cgroup"]
CMD ["/usr/lib/systemd/systemd"]

FROM base AS lamp
RUN dnf install -y \
    https://rpms.remirepo.net/enterprise/remi-release-8.rpm && \
    dnf module reset -y php && \
    dnf module install -y php:remi-7.3 && \
    dnf install -y httpd mariadb-server && \
    dnf autoremove -y && \
    dnf clean all
