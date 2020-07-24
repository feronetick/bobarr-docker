FROM node:current-alpine

WORKDIR /srv

RUN \
  apk add subversion && \
  svn checkout https://github.com/iam4x/bobarr/trunk/packages/web && \
  yarn && \
  yarn build

EXPOSE PORT 3000

HEALTHCHECK --start-period=30s \
  CMD curl -f http://localhost:3000/health || exit 1

CMD ["yarn", "prod"]
