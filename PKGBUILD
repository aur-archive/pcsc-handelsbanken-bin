# Maintainter: JKAbrams <JKAbrams at AUR>

### Installation for Handelsbanken's card reader
# 
#   To make it work, you might need to change the following settings in /etc/opensc.conf
#    use_file_caching = true;
#    lock_login = true;
#   
#   For information how to use this driver together with Fribid, see:
#    http://forum.fribid.se/viewtopic.php?id=78

pkgname=pcsc-handelsbanken-bin
pkgver=1.0.2
pkgrel=3
pkgdesc="PCSC Driver for TODO's Cardreaders used by Handelsbanken"
arch=('i686' 'x86_64')
url="http://www.henriknordstrom.net/code/SHB/"
license=('unknown')
depends=('pcsclite' 'opensc' 'libusb-compat')

[ "$CARCH" = "i686"   ] && _arch="32bit"
[ "$CARCH" = "x86_64" ] && _arch="64bit"
source=("http://www.henriknordstrom.net/code/SHB/shbecrDeb.bundle-${pkgver}-${_arch}.tar.gz")
[ "$CARCH" = "i686"   ] && sha256sums=('9379704260f39d3fe1b28b5aba2e7268b1db36388e5732deb4750080d94f287e')
[ "$CARCH" = "x86_64" ] && sha256sums=('86bee812480cfc5af0847a9f10109b6870f293f4ad8d692232c6e5092038757c')


package() {
	[ "$CARCH" = "i686"   ] && _lib="lib32"
	[ "$CARCH" = "x86_64" ] && _lib="lib"

	mkdir -p $pkgdir/usr/${_lib}/pcsc/drivers
	mv shbecrDeb.bundle $pkgdir/usr/${_lib}/pcsc/drivers/
}
