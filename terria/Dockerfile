# Docker image for the primary terria map application server
FROM node:14

# RUN apt-get update && apt-get install --fix-missing -y gdal-bin

COPY ./src/TerriaMap ./app
WORKDIR /app
COPY ./src/TerriaMap/devserverconfig.json ./productionserverconfig.json
RUN git config --global url."https://".insteadOf git://
RUN yarn
COPY ./Cesium.d.ts ./node_modules/terriajs-cesium/Source/Cesium.d.ts
RUN yarn gulp release


EXPOSE 3001

# COPY ./app /app


# WORKDIR /app


# CMD ["pm2-runtime", "/app/ecosystem-production.config.js", "--update-env", "--env", "production"]

# CMD ["./node_modules/.bin/pm2", "start", "ecosystem-production.config.js", "--update-env", "--env", "production", ">/app/ahoka.txt"]
# CMD ./node_modules/.bin/pm2 start ecosystem-production.config.js --update-env --env production



