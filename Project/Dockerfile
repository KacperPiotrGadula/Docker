# Stage development
FROM ubuntu:22.04 AS development

# Instalacja Apache, ca-certificates i curl z przypisanymi wersjami
RUN apt-get update && apt-get install --no-install-recommends --no-install-suggests -y \
    apache2=2.4.52-1ubuntu4.12 \
    curl=7.81.0-1ubuntu1.18 \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Add non-root user
RUN groupadd -g 3001 prod && \
    useradd -u 3001 -g prod -d /home/prod prod && \
    mkdir /home/prod && chown -R prod:prod /home/prod

ARG NODE_ENV=production
ENV NODE_ENV=$NODE_ENV

COPY index.html /tmp/index.html

RUN chown -R prod:prod /tmp

CMD ["cat", "/tmp/index.html"]

# Stage production
FROM development AS production

# Creating the required directories for Apache
RUN mkdir -p /var/run/apache2 /var/lock/apache2 /var/log/apache2 && \
    chown -R prod:prod /var/www/html /var/log/apache2 /var/run/apache2 /var/lock/apache2 && \
    chmod -R 755 /var/log/apache2

# Copying the index.html
COPY --from=development /tmp/index.html /var/www/html/index.html

# Adding the ServerName configuration
RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

# Addition of HEALTHCHECK for Apache
HEALTHCHECK --interval=30s --timeout=10s --start-period=5s --retries=3 \
    CMD curl -f http://localhost/ || exit 1

# Removing setuid/setgid bits from unnecessary files
RUN chmod g-s /usr/sbin/unix_chkpwd && \
    chmod u-s /usr/bin/newgrp && \
    chmod u-s /usr/bin/passwd && \
    chmod u-s /usr/bin/su && \
    chmod u-s /usr/bin/chfn && \
    chmod u-s /usr/bin/mount && \
    chmod u-s /usr/bin/gpasswd && \
    chmod g-s /usr/bin/expiry && \
    chmod u-s /usr/bin/chsh && \
    chmod u-s /usr/bin/umount && \
    chmod g-s /usr/bin/chage && \
    chmod g-s usr/sbin/pam_extrausers_chkpwd

# Setting up the user who starts Apache
USER prod

CMD ["apache2ctl", "-D", "FOREGROUND"]