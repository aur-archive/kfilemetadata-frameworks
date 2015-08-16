# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=kfilemetadata-frameworks
pkgver=5.0.1
pkgrel=1
pkgdesc="A library for extracting file metadata"
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kde/kdelibs/kfilemetadata'
license=('LGPL')
depends=('kservice' 'karchive' 'exiv2' 'poppler-qt5' 'taglib' 'ffmpeg' 'ebook-tools')
makedepends=('extra-cmake-modules')
source=("http://download.kde.org/stable/plasma/$pkgver/kfilemetadata-$pkgver.tar.xz")
md5sums=('8281f64d0656803f2c2673fa73752477')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../kfilemetadata-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_PREFIX_PATH=/usr/lib/cmake \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLIB_INSTALL_DIR=lib \
    -DQT_PLUGIN_INSTALL_DIR=lib/qt/plugins
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
