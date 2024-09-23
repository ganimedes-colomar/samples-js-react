FROM nodejs:16-ubi8

LABEL "io.openshift.build.commit.author"="ec2-user <arquitectura.devops@correos.com>"       "io.openshift.build.commit.date"="Mon Sep 23 10:08:29 2024 +0000"       "io.openshift.build.commit.id"="11a0b33dda54e797fca865f3548fec9756520b14"       "io.openshift.build.commit.ref"="master"       "io.openshift.build.commit.message"="fix testenv location"       "io.openshift.build.source-location"="https://github.com/ganimedes-colomar/samples-js-react.git"       "io.openshift.build.source-context-dir"="okta-hosted-login"       "io.openshift.build.image"="image-registry.openshift-image-registry.svc:5000/openshift/nodejs@sha256:ec4bda6a4daaea3a28591ea97afc0ea52d06d881a5d966e18269f9c0d0c87892"
ENV OPENSHIFT_BUILD_NAME="react-front-2"     OPENSHIFT_BUILD_NAMESPACE="pruebas-controlm"     OPENSHIFT_BUILD_SOURCE="https://github.com/ganimedes-colomar/samples-js-react.git"     OPENSHIFT_BUILD_COMMIT="11a0b33dda54e797fca865f3548fec9756520b14"

USER root
COPY . /tmp/src
RUN chown -R 1001:0 /tmp/src
COPY ./run /opt/app-root/s2i/bin/

USER 1001
RUN /usr/libexec/s2i/assemble

CMD /usr/libexec/s2i/run
