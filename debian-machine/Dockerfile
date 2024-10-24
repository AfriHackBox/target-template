FROM echothrust/base-bookworm:latest
# of use the following if you need bullseye
# FROM echothrust/base-bullseye:latest
# You can use any image you like as long as it follows the rules
# The existing tags for each of the provided images can be found at
# https://hub.docker.com/r/echothrust/base-bullseye/tags and
# https://hub.docker.com/r/echothrust/base-bookworm/tags
LABEL maintainer="Your name <Your email or platform profile url>"
LABEL description="A small description"

#####################
# ENV AND BUILD ARGS
#####################
ENV DEBIAN_FRONTEND noninteractive
ADD 01_nodoc /etc/dpkg/dpkg.cfg.d/
COPY *.yml /tmp/
COPY entrypoint.sh /
COPY supervisord.conf /etc/supervisord.conf
#COPY your-files-here /at/some/place

# PACKAGE INSTALLATIONS
RUN set -ex \
    && apt-get update \
    && apt-get install --no-install-recommends -y tini openssh-server openssh-client \
    && ansible-playbook -i 'localhost,' /tmp/autoregister.yml \
    && chmod 0500 /entrypoint.sh \
    && rm -rf /usr/src/* /var/lib/apt/lists/* /tmp/* /usr/share/locale/* /usr/share/man/* /usr/share/doc/*


HEALTHCHECK NONE

# RUNTIME
WORKDIR /
ENTRYPOINT ["tini","--", "/entrypoint.sh"]
CMD ["supervisord -c /etc/supervisord.conf"]
