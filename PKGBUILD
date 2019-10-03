# Maintainer: Tomislav Ivek <tomislav.ivek@gmail.com>

pkgname=('conan')
pkgver=1.19.1
pkgrel=1
pkgdesc="A distributed, open source, C/C++ package manager."
arch=('any')
url="https://conan.io"
license=('MIT')
makedepends=('python-setuptools')
depends=('python-pyjwt>=1.4.0'
         'python-requests>=2.8.1'
         'python-colorama>=0.3.3'
         'python-yaml>=3.11'
         'python-patch>=1.16'
         'python-fasteners>=0.14.1'
         'python-six>=1.10.0'
         'python-node-semver>=0.6.1'
         'python-bottle>=0.12.8'
         'python-distro>=1.0.2'
         'python-pluginbase>=0.5'
         'python-pylint>=2.3.1'
         'python-future>=0.16.0'
         'python-pygments>=2.0'
         'python-astroid>=1.6.5'
         'python-deprecation>=2.0'
         'python-tqdm>=4.28.1'
         'python-jinja>=2.3'
         'python-dateutil>=2.7.0')
source=("https://github.com/conan-io/conan/archive/${pkgver}.tar.gz" "arch-reqs.patch")

 prepare() {
  cd $pkgname-$pkgver
  patch -Np1 -i "${srcdir}/arch-reqs.patch"
 }

build() {
  cd "$srcdir/conan-$pkgver"
  python setup.py build
}

package() {
  cd "$srcdir/conan-$pkgver"
  python setup.py install --optimize=1 --root=${pkgdir}
  install -m755 -d "${pkgdir}/usr/share/licenses/conan"
  install -m644 LICENSE.md "${pkgdir}/usr/share/licenses/conan/"
  install -m755 -d "${pkgdir}/usr/share/doc/conan"
  install -m644 contributors.txt "${pkgdir}/usr/share/doc/conan/"
}
md5sums=('5a0f47cc0f24cc781f4af9055ba77bd4'
         '6f42135bf44d5832bb729c7855560d97')
