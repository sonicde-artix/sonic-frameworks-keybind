# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-frameworks-keybind
pkgver=6.27.0
pkgrel=2
pkgdesc='sonic-frameworks-keybind allows to have global accelerators that are independent of the focused window'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-frameworks-keybind'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(glibc
         libgcc
         qt6-base)
makedepends=(doxygen
             qt6-tools
             sonic-frameworks-cmake-modules)
conflicts=('kglobalaccel')
provides=('kglobalaccel')
replaces=('kglobalaccel')
groups=(sonicde-frameworks)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('d1edb69cee5ca8b6ca5177348f3e66c35da7f59f9bbbc8d1ee21a2d083e6680f')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DCMAKE_INSTALL_LIBDIR=lib \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
