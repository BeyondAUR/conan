# Maintainer: Tomislav Ivek <tomislav.ivek@gmail.com>

pkgname=('conan')
pkgver=0.14.1
pkgrel=1
pkgdesc="A distributed, open source, C/C++ package manager."
arch=('any')
url="https://conan.io"
license=('MIT')
makedepends=('python-setuptools')
depends=('python-pyjwt>=1.4.0' 'python-pyjwt<1.5.0'
         'python-requests>=2.7.0' 'python-requests<2.12.0'
         'python-colorama>=0.3.3' 'python-colorama<0.4.0'
         'python-passlib>=1.6.5' 'python-passlib<1.7.0'
         'python-boto>=2.38.0' 'python-boto<2.44.0'
         'python-yaml>=3.11' 'python-yaml<3.13.0'
         'python-patch=1.16'
         'python-fasteners>=0.14.1'
         'python-six>=1.10.0'
         'python-bottle>=0.12.8' 'python-bottle<0.13')
source=("https://github.com/conan-io/conan/archive/${pkgver}.tar.gz")
sha512sums=('e60cc9ab52bdfed8c4148af24b8dfac5d17583f6dff9e956fc6a614f1a995473b873004bd762064ca42cfdacd3d7924bb0079c0ac09a140f1218b47c20172c91')

build() {
  cd "$srcdir/conan-$pkgver"
  python setup.py build
}

package() {
  cd "$srcdir/conan-$pkgver"
  python setup.py install --optimize=1 --root=${pkgdir}
  install -m755 -d "${pkgdir}/usr/share/licenses/conan"
  install -m644 LICENSE.md "${pkgdir}/usr/share/licenses/conan/"
}
