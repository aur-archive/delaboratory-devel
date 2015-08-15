# Maintainer: speps <speps at aur dot archlinux dot org>

_name=delaboratory
pkgname=$_name-devel
pkgver=0.7.4
pkgrel=1
pkgdesc="A realtime color correction utility, development version."
arch=(i686 x86_64)
url="http://code.google.com/p/delaboratory/"
license=('GPL3')
depends=('wxgtk' 'desktop-file-utils')
optdepends=('dcraw: RAW files support')
provides=("$_name=$pkgver")
install="$pkgname.install"
source=("http://$_name.googlecode.com/files/$_name-$pkgver.tar.gz"
        "$pkgname.desktop")
md5sums=('fcec04ce07924b9aa8923dd8e292dead'
         '9d189e926a1d75bedf756e363f3f5df0')

build() {
  cd "$srcdir/$_name-$pkgver"

  [ "$CARCH" = x86_64 ] && _arch=64
  make ARCH=$_arch
}

package() {
  cd "$srcdir/$_name-$pkgver"

  # bin
  install -Dm755 $_name \
    "$pkgdir/usr/bin/$pkgname"

  # desktop file
  install -Dm644 ../$pkgname.desktop \
    "$pkgdir/usr/share/applications/$pkgname.desktop"
}

# vim:set ts=2 sw=2 et:
