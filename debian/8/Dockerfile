FROM debian:8

RUN apt-get update && apt-get upgrade -y && \
    apt-get install --no-install-recommends -y \
        openssh-client \
        openssh-server \
        python3 \
        python3-pip \
        sudo \
	systemd && \
    apt-get autoremove -y && \
    apt-get clean -y && \
    rm -rf \
        /lib/systemd/system/{*getty*,systemd*udev*} && \
    cp /bin/true /sbin/agetty && \
    echo "Defaults !requiretty" >> /etc/sudoers

VOLUME ["/sys/fs/cgroup"]
CMD ["/lib/systemd/systemd"]
