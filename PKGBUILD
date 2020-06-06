# Original Contributor Dan McGee <dan@archlinux.org>
# Contributor: Florian Zeitz <florob at babelmonkeys dot de>
# Mantainer:  Lorenzo Ferrillo <lorenzofer at live dot it> 
_basename=numactl
pkgname=lib32-numactl
pkgver=2.0.13
pkgrel=1
pkgdesc="Simple NUMA policy support 32-bit version. Libraries only"
arch=('x86_64')
url="http://oss.sgi.com/projects/libnuma/"
license=('LGPL2.1' 'GPL2')
depends=('perl' 'numactl')
source=('https://github.com/numactl/numactl/releases/download/v2.0.13/numactl-2.0.13.tar.gz')
md5sums=('9a9a94bfebf6c9c67defeedc9795e568')

build() {
  export CC="gcc -m32"
  export CXX="g++ -m32"
  export PKG_CONFIG_PATH="/usr/lib32/pkgconfig"
  cd "$srcdir/$_basename-${pkgver/_/-}"
  ./configure --prefix=/usr --libdir=/usr/lib32
  make
}

package() {
  cd "$srcdir/$_basename-${pkgver/_/-}"
  make DESTDIR="$pkgdir" install
  rm -rf "$pkgdir/usr/share/" "$pkgdir/usr/bin/" "$pkgdir/usr/include/"
}
 
