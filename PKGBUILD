# Maintainer: nandub <nandub+arch@nandub.info>
# Contributor: Kim Walisch <kim.walisch@gmail.com>

pkgname=primesieve
pkgver=7.4
pkgrel=1
pkgdesc="A fast prime number generation program and C/C++ library"
url="https://github.com/kimwalisch/primesieve"
license=('BSD')
depends=('gcc-libs')
makedepends=('cmake' 'help2man')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/kimwalisch/primesieve/archive/v${pkgver}.tar.gz")
sha1sums=('72aa38a72a07a87e5fbf6aa1118fa1b1596a8fef')
arch=('x86_64')

build() {
  cd $pkgname-$pkgver
  cmake -DCMAKE_INSTALL_PREFIX=/usr \
        -DBUILD_STATIC_LIBS=OFF .
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install

  install -Dm644 "README.md" "$pkgdir/usr/share/doc/$pkgname/README.md"
  install -Dm644 "COPYING" "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
