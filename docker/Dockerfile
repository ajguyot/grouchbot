From node:14.14.0-alpine3.12

WORKDIR /usr/src/grouchbot

COPY package*.json ./

RUN npm ci --only=production

# Install nodemon for automatic restarts on code changes
RUN npm install -g nodemon

# Write source and configuration files
COPY src/ ./src/
COPY config/ ./config/

ARG ENV
ENV ENV=$ENV

ARG PORT
ENV PORT=$PORT

ENTRYPOINT [ "nodemon", "./src/startup.js" ]
