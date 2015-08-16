# Maintainer: Anton Bazhenov <anton.bazhenov at gmail>
# Contributor: zlbgps<zlbgps@gmail.com>

pkgname=lfhex
pkgver=0.42
pkgrel=2
pkgdesc="A hex editor with support for large files"
arch=('i686' 'x86_64')
url="http://stoopidsimple.com/lfhex"
license=('GPL')
depends=('qt4')
makedepends=('bison' 'flex')
source=("http://stoopidsimple.com/files/${pkgname}-${pkgver}.tar.gz")
md5sums=('419ddac5a9e88beee872f53360193028')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}/src"
  sed -i "22i#include <sys/types.h>" expr.h
  qmake-qt4
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  # Install binary
  install -Dm755 "src/${pkgname}" "${pkgdir}/usr/bin/${pkgname}"

  # Install documentation
  mkdir -p "${pkgdir}/usr/share/doc/${pkgname}"
  install -m644 CONTRIBUTORS README "${pkgdir}/usr/share/doc/${pkgname}"
}
