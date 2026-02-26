# Maintainer: MS-DOS Manfred
pkgname=86box-roms-git
pkgver=f8f076c2ce4cefdea18e88841fefe3400bffcf6e
pkgrel=1
pkgdesc='ROMs for the 86Box emulator'
arch=('any')
url='https://github.com/86Box/roms'
license=('custom')
makedepends=('git')
options=('!strip')
provides=('86box-roms')
conflicts=('86box-roms')
source=("${pkgname}::git+https://github.com/86Box/roms.git")
sha512sums=('SKIP')

pkgver() {
  cd ${pkgname}
  git describe --long --tags | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
  cd "${srcdir}/${pkgname}"
  install -d "$pkgdir/usr/share/86Box/roms"
  cp -R [a-z]* "$pkgdir/usr/share/86Box/roms"
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
