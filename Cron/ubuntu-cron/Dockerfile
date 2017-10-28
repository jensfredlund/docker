FROM ubuntu:xenial
LABEL maintainer "jens.fredlund@gmail.com"
LABEL description="Ubuntu cron example container"
LABEL version="1.0"

# Install stuff and clean up
RUN apt update && \
    apt -y upgrade && \
    apt -y install --no-install-recommends cron && \
    apt -y install --no-install-recommends bash && \
    apt clean && \
    rm -rf /var/lib/apt/lists/*

# Add example cron job
COPY files/cron-example /etc/cron.d/cron-example

# Ensure we have the right permissions on the cron job
RUN chmod 0644 /etc/cron.d/cron-example

# Create logfile
RUN touch /var/log/cron.log

ENTRYPOINT ["/usr/sbin/cron","-f"]
