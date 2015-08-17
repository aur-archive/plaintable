# Maintainer: Stefan Tatschner <stefan@sevenbyte.org>

pkgname=python-plaintable-git
pkgname=plaintable
pkgver=r61.d56fd93
pkgrel=1
pkgdesc="A simple library to build plain text tables"
arch=('any')
url="https://github.com/rumpelsepp/plaintable"
license=('MIT')
depends=('python')
makedepends=('python-setuptools')
conflicts=('python-plaintable')
provides=('python-plaintable')
source=("${pkgname}::git+https://github.com/rumpelsepp/plaintable.git")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/${_pkgname}"
  #git describe --long | sed -E 's/([^-]*-g)/r\1/;s/-/./g'
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "$srcdir/$pkgname"
  python setup.py install --prefix=/usr --root="${pkgdir}" --optimize=1
}
