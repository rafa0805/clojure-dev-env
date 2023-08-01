# fix platform to linux/amd64 since clj-style cannot run in arm64 when installed through installer distrubuted at GitHub
FROM --platform=linux/amd64 ubuntu:20.04

RUN apt-get update -y && \
    apt-get install -y curl zip

RUN apt-get install -y openjdk-17-jdk &&\
    apt-get install -y leiningen

# cljstyle
# see: https://github.com/greglook/cljstyle
RUN curl -sLO https://raw.githubusercontent.com/greglook/cljstyle/main/script/install-cljstyle && \
    chmod +x install-cljstyle && \
    ./install-cljstyle && \
    rm ./install-cljstyle

# clj-kondo
# see: https://github.com/clj-kondo/clj-kondo
RUN curl -sLO https://raw.githubusercontent.com/clj-kondo/clj-kondo/master/script/install-clj-kondo && \
    chmod +x install-clj-kondo && \
    ./install-clj-kondo && \
    rm ./install-clj-kondo

# Clojure
# see: https://clojure.org/guides/install_clojure
RUN curl -O https://download.clojure.org/install/linux-install-1.11.1.1347.sh && \
    chmod +x linux-install-1.11.1.1347.sh && \
    ./linux-install-1.11.1.1347.sh && \
    rm ./linux-install-1.11.1.1347.sh

RUN mkdir /workspace

WORKDIR /workspace
