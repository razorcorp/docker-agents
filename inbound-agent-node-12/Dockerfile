FROM jenkins/inbound-agent:alpine

USER root

COPY --from=node:12.11.1-alpine /usr/local/bin/node /usr/local/bin/
COPY --from=node:12.11.1-alpine /usr/local/lib/node_modules /usr/local/lib/
COPY --from=node:12.11.1-alpine /opt/yarn-v1.19.0 /opt

RUN ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npm
RUN ln -s /usr/local/lib/node_modules/npm/bin/npx-cli.js /usr/local/bin/npx
RUN ln -s /opt/yarn-v1.19.0/bin/yarn /usr/local/bin/yarn
RUN ln -s /opt/yarn-v1.19.0/bin/yarnpkg /usr/local/bin/yarnpkg

USER jenkins
