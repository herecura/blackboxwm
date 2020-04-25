# Maintainer: Brian Bidulock <bidulock@openss7.org>

pkgname=blackboxwm
_pkgname=blackbox
pkgver=0.76
pkgrel=1
pkgdesc="A window manager for X11 (maintained fork of blackbox)"
arch=('x86_64')
url="http://github.com/bbidulock/blackboxwm"
license=('MIT')
provides=($_pkgname)
conflicts=($_pkgname)
replaces=($_pkgname)
depends=('libxext' 'libxft')
options=('!libtool' 'staticlibs')
source=("https://github.com/bbidulock/$pkgname/releases/download/$pkgver/$_pkgname-$pkgver.tar.lz")
sha512sums=('d10ce81b2c3ad4cac25f8811d562da831f81e3003ef1469a2a7422d32b3e7d0a17b7b4f9fee02f099197c770d42d94253cc6e856b7895ad76d7cefd7a60dd4c0')

build() {
  cd $_pkgname-$pkgver
  ./configure --enable-static --enable-shared
  make
}

package() {
  cd $_pkgname-$pkgver
  make DESTDIR="$pkgdir" install
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}

# vim:set ts=2 sw=2 et:
