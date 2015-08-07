#!/bin/sh

# Name: install_rofi
# Author: Shion Ryuu<shionryuu@outlook.com>
# This is a script used to install rofi on Ubuntu.
# Test under Ubuntu 14.04 only.

rofi_url="https://github.com/DaveDavenport/rofi/releases/download/0.15.4/rofi-0.15.4.tar.gz"

apt-get update
apt-get upgrade -y --show-upgraded
apt-get install -y libxft-dev libxinerama-dev libpango1.0-dev

if [ ! -s "./rofi.tar.gz" ]; then
    wget -c -O rofi.tar.gz $rofi_url
fi

tar zxvf rofi.tar.gz
cd ./rofi-*/

autoreconf -i
./configure
make && make install
 
apt-get autoclean -y
apt-get clean -y
apt-get autoremove -y
