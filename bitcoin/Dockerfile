FROM gramm/coin-baseimage

RUN git clone https://github.com/bitcoin/bitcoin.git /coin
WORKDIR /coin
RUN chmod 755 ./share/genbuild.sh && ./autogen.sh && ./configure && make

EXPOSE 8332 8333 9051
VOLUME ["/coin-data"]


CMD /coin/src/bitcoind -datadir=/coin-data & tail -f /coin-data/debug.log

