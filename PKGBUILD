# Maintainer: Dan Printzell <xwildn00bx at gmail.com>

_pkgname=wildbar
pkgname=${_pkgname}
pkgver=1
pkgrel=2
pkgdesc='Bar with integrated data providers'
arch=('any')
url='https://github.com/WildN00b/${_pkgname}'
license=('MIT' 'GPL')
depends=('libxcb' 'jansson')
makedepends=('git' 'ninja-git')
source=("git://github.com/WildN00b/${_pkgname}.git")
md5sums=('SKIP')

pkgver() {
    cd "$srcdir/$_pkgname"
    git rev-list --count HEAD
}

build() {
  cd "$srcdir/$_pkgname"
  make
}

package() {
  cd "$srcdir/$_pkgname"
  make DESTDIR="$pkgdir" install
  install -D -m644 LICENSE.bar "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE.bar"
  install -D -m644 LICENSE.wildbar "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE.wildbar"
}