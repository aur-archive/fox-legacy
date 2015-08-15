# $Id: PKGBUILD 8593 2010-01-21 02:12:00Z dgriffiths $
# Contributor: damir <damir@archlinux.org>
# Contributor: Ben <ben@benmazer.net>

pkgname=fox-legacy
pkgver=1.4.35
pkgrel=3
pkgdesc="Free Objects for X: GUI Toolkit for C++ (version 1.4.X)"
arch=('i686' 'x86_64')
url="http://www.fox-toolkit.org/"
license=('LGPL')
options=('!libtool' 'force')
depends=('bzip2' 'cups' 'libxcursor' 'libxft' 'libxrandr' 'mesa')
source=(http://www.fox-toolkit.org/ftp/fox-$pkgver.tar.gz)
md5sums=('9f980f324de6e62f90af7a77d6d0cb2c')

build() {
  cd $startdir/src/fox-$pkgver
  sed -i 's/1.4/1.9/' configure
  ./configure   --prefix=/usr \
                --enable-release \
                --with-xft=yes \
                --enable-cups \
                --with-opengl=yes
  make || return 1
  make DESTDIR=$startdir/pkg/ install || return 1
  rm -r $startdir/pkg/usr/{bin,man}
}
