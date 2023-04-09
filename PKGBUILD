# Maintainer: Johannes Mittendorfer <johannes@johannes-mittendorfer.com>
_pkgname=gr-reveng
pkgname=$_pkgname-git
pkgname=gr-reveng-git
pkgver=r28.b36bfa2
pkgrel=1
pkgdesc="A gnuradio module containing blocks useful for reverse engineering RF signals."
arch=('x86_64')
url="https://github.com/paulgclark/gr-reveng"
license=()
depends=('gnuradio')
source=('git+https://github.com/paulgclark/gr-reveng')
md5sums=('SKIP')

build() {
    cd "$_pkgname"
    cmake -B build
    cmake --build build
}

pkgver() {
  cd "$_pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}

package() {
    cd "$_pkgname"
    DESTDIR="$pkgdir" cmake --install build
}
