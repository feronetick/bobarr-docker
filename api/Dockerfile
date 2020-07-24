FROM node:current-alpine

WORKDIR /srv

RUN \
  apk add subversion && \
  svn checkout https://github.com/iam4x/bobarr/trunk/packages/api /sr && \
  yarn && \
  yarn build

EXPOSE PORT 4000

HEALTHCHECK --start-period=30s \
  CMD curl -f http://localhost:4000/health || exit 1

CMD ["yarn", "prod"]
