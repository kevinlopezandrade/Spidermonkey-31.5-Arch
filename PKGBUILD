# Creator: Kevin Lopez <kevinlopezandrade@gmail.com"

pkgname=spidermonkey
pkgver=31.5.0
pkgrel=1
pkgdesc="Mozilla's JavaScript engine."
arch=('i686' 'x86_64')
url="http://www.mozilla.org/js/spidermonkey/"
license=('MPL')
#depends=()
makedepends=('gcc')
source=("https://people.mozilla.org/~sstangl/mozjs-$pkgver.tar.bz2" "http://kevlopez.com/files/mozjs-35-nullptr.patch") 
md5sums=('b80301403c3e20a2c122b8a0c2c3077e'
         'dca6e488ad4402dce0537736c00566e4')
prepare() {
    cd mozjs-$pkgver/
    patch -Np1 -i "${srcdir}/mozjs-35-nullptr.patch"
}
build() {
	cd mozjs-$pkgver/js/src
    CPPFLAGS="$CPPFLAGS -O2"
	./configure --prefix=/usr
	make
}

package() {
	cd mozjs-$pkgver/js/src
	make DESTDIR="$pkgdir" install
}

