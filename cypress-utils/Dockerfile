FROM cypress/base:14.0.0

WORKDIR /dependencies

ADD package.json /dependencies
ADD package-lock.json /dependencies

RUN npm ci
RUN npx cypress install

