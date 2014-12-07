sudo apt-get install libxml2-dev libproj-dev libudunits2-dev \
                     libnetcdf-dev libgrib-api-dev libjasper-dev libpng12-dev \
                     libjpeg-dev libpq-dev liblog4cpp5-dev \
                     libboost-filesystem-dev libboost-system-dev \
                     libboost-iostreams-dev libboost-program-options-dev \
                     libboost-regex-dev libboost-test-dev \
                     libboost-date-time-dev

sudo apt-get install ftgl-dev libhdf4g-dev libhdf5-serial-dev libtiff4-dev \
                     libqt4-dev proj libmysqlclient-dev libpqxx-dev \
                     libomniorb4-dev omniidl4 libldap2-dev liblog4cpp5-dev \
                     libcurl4-gnutls-dev libgeotiff-dev libboost-thread-dev
                     
sudo apt-get install libemos-dev libgrib-api-dev libshp-dev libavformat-dev libxt-dev
or
sudo apt-get install libemos-dev libgrib-api-dev libshp-dev libxt-dev

METLIBS:
#/bin/sh

set -e

THIS_DIR=`pwd`

cd $THIS_DIR/common/miLogger/trunk
./autogen.sh && ./configure && make
sudo make install

cd $THIS_DIR/common/puCtools/trunk
./autogen.sh && ./configure && make
sudo make install

cd $THIS_DIR/common/puTools/trunk
./autogen.sh && ./configure && make
sudo make install

cd $THIS_DIR/tseries-support/puDatatypes/trunk
./autogen.sh && ./configure && make
sudo make install

cd $THIS_DIR/diana-support/diField/trunk
./autogen.sh && ./configure && make
sudo make install

cd $THIS_DIR/diana-support/miRaster/trunk
./autogen.sh && ./configure --with-geotiff && make
sudo make install

cd $THIS_DIR/gl-support/glp/trunk
./autogen.sh && ./configure && make
sudo make install

cd $THIS_DIR/gl-support/miFTGL/trunk
./autogen.sh && ./configure && make
sudo make install

cd $THIS_DIR/gl-support/glText/trunk
./autogen.sh && ./configure --enable-xfonts && make
sudo make install

cd $THIS_DIR/qt-utilities/qUtilities/trunk
./autogen.sh && ./configure && make
sudo make install

cd $THIS_DIR/qt-utilities/coserver/trunk
./autogen.sh && ./configure && make
sudo make install
Fedora 20

#/bin/sh

set -e

THIS_DIR=`pwd`

cd $THIS_DIR/common/miLogger/trunk
./autogen.sh && ./configure --prefix=/usr/local && make
sudo make install

cd $THIS_DIR/common/puCtools/trunk
./autogen.sh && ./configure --prefix=/usr/local && make
sudo make install

cd $THIS_DIR/common/puTools/trunk
./autogen.sh && ./configure --prefix=/usr/local && make
sudo make install

cd $THIS_DIR/tseries-support/puDatatypes/trunk
./autogen.sh && ./configure --prefix=/usr/local && make
sudo make install

cd $THIS_DIR/diana-support/diField/trunk
./autogen.sh && ./configure --prefix=/usr/local --with-udunits2-includedir=/usr/include/udunits2 && make
sudo make install

cd $THIS_DIR/diana-support/miRaster/trunk
./autogen.sh && ./configure --prefix=/usr/local --with-geotiff && make
sudo make install

cd $THIS_DIR/gl-support/glp/trunk
./autogen.sh && ./configure --prefix=/usr/local && make
sudo make install

cd $THIS_DIR/gl-support/miFTGL/trunk
./autogen.sh && ./configure --prefix=/usr/local && make
sudo make install

cd $THIS_DIR/gl-support/glText/trunk
./autogen.sh && ./configure --prefix=/usr/local --enable-xfonts && make
sudo make install

cd $THIS_DIR/qt-utilities/qUtilities/trunk
./autogen.sh && ./configure --prefix=/usr/local && make
sudo make install

cd $THIS_DIR/qt-utilities/coserver/trunk
./autogen.sh && ./configure --prefix=/usr/local && make
sudo make install


DIANA

./autogen.sh
./configure --enable-xlib --enable-geotiff --enable-vcross-v2

