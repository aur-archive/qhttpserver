# Maintainer: Christian Bühler <christian.buehler@ipoplan.de>
pkgname=qhttpserver
pkgver=55.91b79bf
pkgrel=1
pkgdesc="A Qt HTTP Server - because hard-core programmers write web-apps in C++ :)"
arch=('i686' 'x86_64')
url="https://github.com/nikhilm/qhttpserver"
license=('BSD')
depends=('qt4')
makedepends=('git')
source=(git+https://github.com/nikhilm/qhttpserver.git)
md5sums=('SKIP')
options=('!makeflags') # https://github.com/nikhilm/qhttpserver/issues/8

pkgver() {
  cd qhttpserver
  echo $(git rev-list --count master).$(git rev-parse --short master)
}

build() {
  cd "$srcdir/$pkgname"
  qmake-qt4
  make
}

package() {
  cd "$srcdir/$pkgname"
  mkdir -p "$pkgdir/usr/include"
  cp src/*.h "$pkgdir/usr/include/"
  cp -r lib "$pkgdir/usr/"
  install -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
