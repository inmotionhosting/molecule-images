FROM centos:8
RUN dnf install -y hostname openssh openssh-server python3 sudo which && \
    dnf autoremove -y && \
    dnf clean all
RUN rm -rf /lib/systemd/system/{*getty*,systemd*udev*} && \
    cp /bin/true /usr/sbin/agetty && \
    echo "Defaults !requiretty" >> /etc/sudoers
VOLUME ["/sys/fs/cgroup"]
CMD ["/usr/lib/systemd/systemd"]
