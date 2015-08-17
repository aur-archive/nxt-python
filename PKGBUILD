# Maintainer: Florian Léger <florian6 dot leger at laposte dot fr>

pkgname=nxt-python
pkgver=2.2.2
pkgrel=3
pkgdesc="A Python driver/interface for the Lego Mindstorms NXT robot."
arch=('any')
url='http://code.google.com/p/nxt-python/'
license=('GPL')
depends=('python2>=2.6 lego-udev-rules')
optdepends=('python-pybluez: for Bluetooth support'
            'pyusb: for USB support'
)
makedepends=('python2-distribute')
source=("http://nxt-python.googlecode.com/files/${pkgname}-${pkgver}.tar.gz")
md5sums=('39b76db07ba22811651555ed33c35821')

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  find -type f -print0 | xargs -0 sed -i -e 's/#!\/usr\/bin\/env python/#!\/usr\/bin\/env python2/g'
  python2 setup.py install --root="${pkgdir}" --optimize=1 || return 1
}

