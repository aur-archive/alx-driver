# Mantainer: Ivan de Jesús Pompa García <ivan.pompa@gmx.com>

pkgname=('alx-driver')
pkgver=20120927
pkgrel=1
pkgdesc='Atheros alx Linux ethernet device driver'
arch=('i686' 'x86_64')
url='http://linuxwireless.org/'
license=('custom')
install=alx-driver.install
source=(http://linuxwireless.org/download/compat-wireless-2.6/compat-wireless-2012-09-27-pc.tar.bz2)

md5sums=('908beda5342abde068c5a6078c9f9458')

build() {
	cd ${srcdir}/compat-wireless-2012-09-27-pc
	./scripts/driver-select alx
	make
	cd ${srcdir}/compat-wireless-2012-09-27-pc/compat
	gzip -9 compat.ko
	install -D -m 0644 compat.ko.gz ${pkgdir}/lib/modules/`uname -r`/updates/compat/compat.ko.gz
	cd ${srcdir}/compat-wireless-2012-09-27-pc/drivers/net/ethernet/atheros/alx
	gzip -9 alx.ko
	install -D -m 0644 alx.ko.gz ${pkgdir}/lib/modules/`uname -r`/updates/drivers/net/ethernet/atheros/alx/alx.ko.gz
}
