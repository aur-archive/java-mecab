# Maintainer: mitsuse <mitsuset - gmail>
pkgname=java-mecab
pkgver=0.993
pkgrel=2
pkgdesc="Morphological Analysis Tool - Java interface"
arch=('i686' 'x86_64')
url="http://mecab.sourceforge.net/"
license=('BSD' 'LGPL' 'GPL')
groups=()
depends=("java-environment" "mecab")
makedepends=("gcc" "sed")
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
source=("http://mecab.googlecode.com/files/mecab-java-$pkgver.tar.gz")
md5sums=('a5a3e38a6a4c7eaf6eec2773efda3124')

build() {
  if [ -f /etc/profile.d/openjdk6.sh ];
  then
    source /etc/profile.d/openjdk6.sh
  elif [ -f /etc/profile.d/jdk.sh ];
  then
    source /etc/profile.d/jdk.sh
  fi
  cd $srcdir/mecab-java-$pkgver
  sed -i '6d' Makefile
  sed -i "6i INCLUDE=${J2SDKDIR}/include" Makefile
  make
}

package() {
  cd $srcdir/mecab-java-$pkgver
  install -d $pkgdir/usr/share/java/mecab
  install -d $pkgdir/usr/lib
  install -m744 MeCab.jar $pkgdir/usr/share/java/mecab
  install -m755 libMeCab.so $pkgdir/usr/lib/
}
