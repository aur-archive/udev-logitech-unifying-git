# Maintainer: Diego <cdprincipe@at@gmail@dot@com>

pkgname=udev-logitech-unifying-git
pkgver=0.9.1.454fbcbc6e
pkgrel=1
pkgdesc="udev rules for Logitech Unifyng and Nano receivers"
url="http://pwr.github.com/Solaar/"
license=('GPL2')
groups=()
arch=('any')
depends=()
provides=('udev-logitech-unifying')
conflicts=('udev-logitech-unifying')
options=(!emptydirs)
install=udev-logitech.install
source=("https://raw.github.com/pwr/Solaar/master/rules.d/42-logitech-unify-permissions.rules" 
        "https://raw.github.com/pwr/Solaar/master/lib/solaar/__init__.py"
        'udev-logitech.install')
md5sums=('SKIP'
         'SKIP'
         '3b153a449bbc44c61ab206c97ab182be')

pkgver() {
  echo $(cat "$srcdir/__init__.py" | grep version | grep -o '[0-9].*[0-9]').$(git ls-remote https://github.com/pwr/Solaar HEAD | head -c 10)
}


package() {
  cd $srcdir
  install -Dm644 "42-logitech-unify-permissions.rules" "$pkgdir/etc/udev/rules.d/42-logitech-unify-permissions.rules"
}
