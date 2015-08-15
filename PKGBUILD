# Maintainer: Boris Timofeev <mashin87@gmail.com>
pkgname=emuchip
pkgver=0.3
pkgrel=2
pkgdesc="a CHIP-8 and Super CHIP emulator"
arch=('i686' 'x86_64')
url="http://code.google.com/p/emuchip/"
license=('GPL3')
depends=('sdl' 'qt4')
makedepends=()
install=
source=("http://emuchip.googlecode.com/files/${pkgname}-${pkgver}-src.tar.bz2" "emuchip.desktop")
md5sums=('fd4020227799f7c27491135a9ea5691a'
         '97069af099d6c6e0a221ebf911968c27')

build() {
  cd $srcdir/${pkgname}-${pkgver}-src
  qmake-qt4
  make
  
  rm -rf ./build/*
  make -f Makefile.emuchip-sdl
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}-src
  install -Dm755 ./bin/${pkgname} ${pkgdir}/usr/bin/${pkgname}
  install -Dm755 ./bin/${pkgname}-sdl ${pkgdir}/usr/bin/${pkgname}-sdl
  install -Dm644 ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/${pkgname}.desktop
  install -Dm644 ./README ${pkgdir}/usr/share/doc/${pkgname}/README
}
