#!/bin/sh

erl_url="http://www.erlang.org/download/otp_src_17.0.tar.gz"
prefix="/usr/local/erlang"

apt-get update
apt-get upgrade -y --show-upgraded
 
apt-get install -y build-essential

apt-get install -y m4 fop libncurses5-dev openssl libssl-dev tk unixodbc unixodbc-dev freeglut3-dev libwxgtk2.8-dev xsltproc

if [ ! -s "./erlang_otp.tar.gz" ]; then
    wget -c -O erlang_otp.tar.gz $erl_url
fi

tar zxvf erlang_otp.tar.gz
cd ./otp_src*/

./configure --prefix=$prefix --without-javac \
    --enable-kernel-poll \
    --enable-threads \
    --enable-dynamic-ssl-lib \
    --enable-shared-zlib \
    --enable-smp-support \
    --enable-hipe

make && make install

ln -sfv $prefix/bin/* /usr/local/bin/

apt-get autoclean -y
apt-get clean -y
apt-get autoremove -y

erl -noshell -eval "erlang:display('Erlang Success Install')" -s init stop
