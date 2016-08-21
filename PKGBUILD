# Maintainer: Tomislav Ivek <tomislav.ivek@gmail.com>

pkgname=('conan')
pkgver=0.11.0
pkgrel=1
pkgdesc="A distributed, open source, C/C++ package manager."
arch=('any')
url="https://conan.io"
license=('MIT')
makedepends=('python-setuptools')
source=(https://github.com/conan-io/conan/archive/$pkgver.tar.gz)
sha512sums=('ee27e0e01b4186ecd7e9e2bdf45f433f4313df9a5ddcc98f0d607442eaa96225e44fee12c3b58576b153bc32095d759bc76833eb6a45c263fa703862f69ee95e')

build() {
  cd "$srcdir/conan-$pkgver"
  python setup.py build
}

package() {
  depends=('python-pyjwt>=1.4.0' 'python-pyjwt<1.5.0'
           'python-requests>=2.7.0' 'python-requests<2.11.0'
           'python-colorama>=0.3.3' 'python-colorama<0.4.0'
           'python-passlib>=1.6.5' 'python-passlib<1.7.0'
           'python-boto>=2.38.0' 'python-boto<2.43.0'
           'python-yaml>=3.11' 'python-yaml<3.12.0'
           'python-patch=1.16'
           'python-fasteners>=0.14.1'
           'python-six>=1.10.0'
           'python-bottle>=0.12.8' 'python-bottle<0.13')

  cd "$srcdir/conan-$pkgver"
  python setup.py install --optimize=1 --root=${pkgdir}
  install -m755 -d "${pkgdir}/usr/share/licenses/conan"
  install -m644 LICENSE.md "${pkgdir}/usr/share/licenses/conan/"
}
