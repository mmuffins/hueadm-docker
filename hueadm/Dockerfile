# label values are passed at build time
LABEL org.opencontainers.image.title=""
LABEL org.opencontainers.image.version=""

FROM node:lts-alpine3.11
RUN npm install hueadm -g
ENTRYPOINT ["hueadm"]