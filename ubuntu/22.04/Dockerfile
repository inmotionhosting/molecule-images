FROM ubuntu:22.04
RUN apt-get update && \
    apt-get install --no-install-recommends -y \
    openssh-client openssh-server python3 sudo systemd && \
    apt-get autoremove -y && \
    apt-get clean -y
RUN rm -rf /lib/systemd/system/{*getty*,systemd*udev*} && \
    cp /bin/true /sbin/agetty && \
    echo "Defaults !requiretty" >> /etc/sudoers
VOLUME ["/sys/fs/cgroup"]
CMD ["/lib/systemd/systemd"]
