# Maintainer: Ecmel Ercan <ecmel dot ercan at gmail dot com>
pkgname=gurgle
#pkgname=('gurgle' 'gurgle-postgresql')
pkgbase='gurgle'
pkgver=1.61
pkgrel=6
pkgdesc="GNU Report Generator Language"
url="http://homepages.inf.ed.ac.uk/timc/gurgle/"
arch=('x86_64' 'i686')
license=('GPL3')
source=("http://homepages.inf.ed.ac.uk/timc/${pkgbase}/${pkgbase}-${pkgver}.tar.gz")
md5sums=('d63138cbd2e6ec63ca8c568e92fbe3c9') 

package_gurgle() {
  cd "${srcdir}/${pkgbase}-${pkgver}"

  ./configure --prefix=/usr
  make
  make DESTDIR="${pkgdir}" install
}

package_gurgle-postgresql() {
  depends=(gurgle postgresql-libs)
  
  cd "${srcdir}/${pkgbase}-${pkgver}"
  ./configure --prefix=/usr --enable-postgres --program-suffix=-psg
  make
  make DESTDIR="${pkgdir}" install

  rm -rf "${pkgdir}/usr/lib" "${pkgdir}/usr/share"
}
