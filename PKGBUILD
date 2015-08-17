# Contributor:	Pablo Lezaeta	<prflr88 @ gmail.com>

pkgname=rox-mouse
_pkgname=Mouse
pkgver=0.10.1.ml
_pkgver=0.10.1
pkgrel=2
pkgdesc="Mouse setter for rox desktop, with manualinux patchs"
group=('rox-desktop')
arch=('any')
url="http://roscidus.com/desktop/Mouse"
license=('GPL')
depends=('rox-lib')
source=(http://manualinux.heliohost.org/archivos/rox/$_pkgname-$_pkgver-ML.tar.bz2
	arch_specific.patch)

build() {
	cd "$srcdir/$_pkgname"
	patch -Np1 -i ../arch_specific.patch
	rm -R Help
	mkdir -p "$pkgdir/usr/share/$pkgname"
	cp -R * "$pkgdir/usr/share/$pkgname"
	cp -R .DirIcon "$pkgdir/usr/share/$pkgname"
	mkdir -p "$pkgdir/usr/bin"
	echo "#!/usr/bin/env bash" > $pkgdir/usr/bin/$pkgname
	echo "/usr/share/$pkgname/AppRun" >> $pkgdir/usr/bin/$pkgname
	chmod +x $pkgdir/usr/bin/$pkgname
}

md5sums=('b59de2f7ca005a57337b23171f1c2b93'
         '882aff247b521c87e786fcd033cb9f91')
