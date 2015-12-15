# tvheadend
How to install
apt-get install git build-essential pkg-config libssl-dev dvb-firmware-osmc dvb-tools libdvbv5-0 liburiparser-dev liburiparser1 libavahi-client-dev zlib1g-dev libavcodec-dev libavutil-dev libavformat-dev libswscale-dev
sudo apt-get install git build-essential pkg-config libssl-dev dvb-firmware-osmc dvb-tools libdvbv5-0 liburiparser-dev liburiparser1 libavahi-client-dev zlib1g-dev libavcodec-dev libavutil-dev libavformat-dev libswscale-dev
sudo apt-get install gettext
sudo apt-get install unzip libcurl4-openssl-dev pkg-config git build-essential dvb-apps libssl-dev
sudo apt-get install libavahi-client-dev libavcodec-dev libavfilter-dev libavformat-dev libavutil-dev libswscale-dev libavcodec-extra-53 liburiparser1 liburiparser-dev debhelper libcurl4-gnutls-dev a52dec
sudo apt-get install openssl
sudo apt-get install git build-essential libavcodec-dev libavformat-dev libssl-dev   libavutil-dev libavahi-client-dev libcurl3   w-scan
sudo apt-get install libiconv* liburiparser*
sudo apt-get install libiconv-hook1 libiconv-hook-dev

cd /usr/src
git clone git://git.videolan.org/x264
cd x264
./configure --host=arm-unknown-linux-gnueabi --enable-static --disable-opencl
sudo make
sudo make install

https://github.com/jordy33/lame.git
cd lame
./configure
sudo make
make install

cd /usr/src
git clone git://source.ffmpeg.org/ffmpeg.git
cd ffmpeg
sudo ./configure --arch=armel --target-os=linux --enable-gpl --enable-libx264 --enable-nonfree
make
sudo make install

cd /usr/src/tvheadend/data
mkdir dvb-scan
cd dvb-scan
sudo cp /usr/share/dvb . -fr

cd /usr/src/tvheadend
// sudo ./configure
sudo ./configure --disable-libav
sudo make
