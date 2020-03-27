# Package maintainer: airwoodix <airwoodix at posteo dot me>

pkgname=hdf5-zstd-filter-git
pkgver=r6.gd5afdb5
pkgrel=1
pkgdesc="ZSTD filter for the HDF5 data format"
arch=('i686' 'x86_64')
url="https://github.com/aparamon/HDF5Plugin-Zstandard"
license=('Apache')
depends=('hdf5')
makedepends=('git' 'cmake')
source=("${pkgname%-git}::git+https://github.com/aparamon/HDF5Plugin-Zstandard")
md5sums=('SKIP')
sha256sums=('SKIP')

pkgver() {
    cd "${pkgname%-git}"
    printf "r%s.g%s" "$(git rev-list --count HEAD)" \
	   "$(git rev-parse --short HEAD)"
}

build() {
    cd "${srcdir}/${pkgname%-git}"
    cmake . -DCMAKE_INSTALL_PREFIX=/usr
    make
}

package() {
    cd "${srcdir}/${pkgname%-git}"
    make DESTDIR="${pkgdir}/" install
}
