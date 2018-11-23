pkgname=lsdvd
pkgver=0.17
pkgrel=1
pkgdesc="Console application that displays the content of a DVD"
arch=('x86_64')
url="https://sourceforge.net/projects/lsdvd/"
license=('GPL2')
depends=('libdvdread')
source=(https://downloads.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('32e63ff932ee2867e023ad3e74e14dcb')

build() {
  cd $pkgname-$pkgver
  msg "### configure"
  ./configure --prefix=/usr
  msg "### make"
  make
}

package() {
  cd $pkgname-$pkgver
  msg "### make install"
  make DESTDIR="$pkgdir" install
  _docdir=${pkgdir}/usr/share/doc/${pkgname}
  _licdir=${pkgdir}/usr/share/licenses/${pkgname}
  install -dm755 ${_docdir} ${_licdir}
  install -Dpm644 AUTHORS ChangeLog INSTALL README ${_docdir}/
  install -Dpm644 COPYING ${_licdir}/
}
