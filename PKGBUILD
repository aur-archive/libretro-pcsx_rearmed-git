# Maintainer:  prettyvanilla <prettyvanilla@posteo.at>
# Contributor: almostalive   <almostalive2003 at gmail dot com>

pkgname=libretro-pcsx_rearmed-git
pkgver=1008.496d559
pkgrel=1
pkgdesc="libretro implementation of PCSX ReARMed. (PlayStation)"
arch=('i686' 'x86_64' 'arm' 'armv6h')
url="https://github.com/libretro/pcsx_rearmed"
license=('GPL')
depends=('zlib')
makedepends=('git')

_gitname=pcsx_rearmed
source=("git+https://github.com/libretro/${_gitname}.git"
        "https://raw.github.com/libretro/libretro-super/master/dist/info/pcsx_rearmed_libretro.info")
md5sums=('SKIP'
         'SKIP')

pkgver() {
  cd "${_gitname}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${_gitname}"
  ./configure --platform=libretro
  make
}

package() {
  install -Dm644 "${_gitname}/libretro.so" "${pkgdir}/usr/lib/libretro/libretro-pcsx_rearmed.so"
  install -Dm644 "pcsx_rearmed_libretro.info" "${pkgdir}/usr/lib/libretro/libretro-pcsx_rearmed.info"
}
