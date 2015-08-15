# Maintainer: Yosef Or Boczko <yoseforb@gmail.com>

_pkgname=gnome-devel-docs
pkgname=$_pkgname-git
pkgver=3.8.1.134.g138c0ed
pkgrel=1
pkgdesc="GNOME Developer documentation (incl. HIG, Platform Guide, a11y Guide, etc.)"
arch=('any')
url="http://developer.gnome.org/"
license=('GPL')
depends=('yelp')
makedepends=('gnome-common' 'gnome-doc-utils')
replaces=('gnome-devel-docs')
provides=('gnome-devel-docs' 'gnome-devel-docs=3.8.1')
conflicts=('gnome-devel-docs')
source=('git://git.gnome.org/gnome-devel-docs')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  git describe --always | sed 's|-|.|g'
}

build() {
  cd "$srcdir/$_pkgname"
  
  ./autogen.sh --prefix=/usr --sysconfdir=/etc --localstatedir=/var
  make
}

package() {
  cd "$srcdir/$_pkgname"  
  make DESTDIR="$pkgdir" install
}
