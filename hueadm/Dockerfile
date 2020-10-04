# label values are passed at build time
LABEL org.opencontainers.image.title="title"
LABEL org.opencontainers.image.version="0.9"

FROM node:lts-alpine3.11
RUN npm install hueadm -g
ENTRYPOINT ["hueadm"]