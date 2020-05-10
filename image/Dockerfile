FROM ubuntu:16.04

RUN apt-get update && apt-get clean && apt-get install -y \
    x11vnc \
    xvfb \
    fluxbox \
    wmctrl \
    wget \
    && wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
    && echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list \
    && apt-get update && apt-get -y install google-chrome-stable

RUN useradd apps \
    && mkdir -p /home/apps \
    # && chown -v -R apps:apps /home/apps \
    && mkdir /.fluxbox \
    && mkdir /tmp \
    && touch /.fehbg \
    && touch /.x11vnc.pass \
    && chmod -R 777 /home/apps \
    && chmod -R 777 /.fluxbox \
    && chmod -R 777 /.fehbg \
    && chmod -R 777 /.x11vnc.pass \
    && chmod -R 777 /tmp
    
EXPOSE 5900

COPY bootstrap.sh /
CMD '/bootstrap.sh'
