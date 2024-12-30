FROM registry.suse.com/suse/sle15:15.5
LABEL maintainer="Anthony Tortola <atortola@suse.com>"

ARG repo
ARG cert

RUN echo "$cert" > /etc/pki/trust/anchors/RHN-ORG-TRUSTED-SSL-CERT.pem
RUN update-ca-certificates
RUN echo "$repo" > /etc/zypp/repos.d/susemanager:dockerbuild.repo

ADD add_pg_packages.sh /root/add_packages.sh
RUN /root/add_pg_packages.sh
