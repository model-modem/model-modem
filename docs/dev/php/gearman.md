# Gearman

Gearman is (as far as I can tell) a now defunct message queue system that made it relatively easy to send messages from one script to another.  I used Gearman extensively with PHP in days of yore.  I would not recommend you do this today.

```bash
RUN apt-get install -y libboost-all-dev gperf libevent-dev uuid-dev
RUN wget https://github.com/gearman/gearmand/releases/download/${GEARMAND_VERSION}/gearmand-${GEARMAND_VERSION}.tar.gz && \
    tar -xzf gearmand-${GEARMAND_VERSION}.tar.gz && \
    cd gearmand-${GEARMAND_VERSION} && \
    ./configure && \
    make && \
    make install
```