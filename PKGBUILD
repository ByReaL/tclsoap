# Contributor: Mircea Dan Gheorghe <mirceadan@gmail.com>
# Maintainer: Mircea Dan Gheorghe <mirceadan@gmail.com>

pkgname=tclsoap
pkgver=1.6.7
pkgrel=1
pkgdesc="The TclSOAP package provides a mechanism to bind Tcl command procedures to remote procedure calls using the Simple Object Access Protocol (SOAP) and XML-RPC over HTTP. Both client and server code is provided."
url="http://tclsoap.sourceforge.net"
arch=('i686' 'x86_64')
license=('MIT')
depends=('tcl' 'tclxml')
optdepends=(
    'tdom: technically not needed, but you want it if you want this package'
    'tcllib: technically not needed, but you want it if you want this package'
)
source=("https://sourceforge.net/projects/tclsoap/files/tclsoap/TclSOAP-$pkgver/TclSOAP-$pkgver.tar.gz")
md5sums=('6e07a5dad13233851fc9eecd9f7319e1')

build() {
  cd $srcdir/$pkgname$pkgver
  ./configure --prefix=/usr
  make
}
package() {
  cd $srcdir/$pkgname$pkgver
  make DESTDIR=$pkgdir install
  install -Dm644 LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
  install -d $pkgdir/usr/share/doc/$pkgname
  cp -r doc/* $pkgdir/usr/share/doc/$pkgname
  rmdir $pkgdir/usr/bin
}