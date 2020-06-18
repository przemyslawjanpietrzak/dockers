FROM cypress/browsers:node12.8.1-chrome80-ff72

WORKDIR /dependencies

USER root

ADD package.json /dependencies
ADD package-lock.json /dependencies

# install Chrome browser
ENV CHROME_VERSION 80.0.3987.116
RUN wget -O /usr/src/google-chrome-stable_current_amd64.deb "http://dl.google.com/linux/chrome/deb/pool/main/g/google-chrome-stable/google-chrome-stable_${CHROME_VERSION}-1_amd64.deb" && \
  dpkg -i /usr/src/google-chrome-stable_current_amd64.deb ; \
  apt-get install -f -y && \
  rm -f /usr/src/google-chrome-stable_current_amd64.deb

RUN npm ci
RUN npx cypress install

