# $Id: PKGBUILD 120246 2014-10-06 12:31:33Z flexiondotorg $
# Maintainer : Martin Wimpress <code@flexion.org>

pkgname=mate-applet-softupd
pkgver=0.2.11
pkgrel=1
pkgdesc="A MATE panel applet to notify when software updates become available."
url="http://www.zavedil.com/mate-software-updates-applet/"
arch=('i686' 'x86_64')
license=('GPL')
depends=('gnome-packagekit' 'gtk2' 'libnotify' 'mate-panel')
makedepends=('mate-common' 'perl-xml-parser' 'yelp-tools')
source=("http://www.zavedil.com/wp-content/uploads/2014/04/${pkgname}-${pkgver}.tar.gz")
sha256sums=('adeb4c12bc2a43c3727e0acac56f28f247939ed1b28ee2700f57042e7b284f4d')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${pkgname}
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
    rm -f "${pkgdir}/usr/share/glib-2.0/schemas/gschemas.compiled"
}
