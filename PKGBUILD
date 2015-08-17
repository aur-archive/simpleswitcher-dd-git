# Maintainer: Eric Engestrom <aur [at] engestrom [dot] ch>
# Contributor: Sean Pringle <sean.pringle@gmail.com>
# Contributor: SanskritFritz (gmail)

pkgname=simpleswitcher-dd-git
_gitname=simpleswitcher
pkgver=r164.1bed425
pkgrel=1
pkgdesc="Popup window switcher roughly based on superswitcher, requiring only xlib and xft. DaveDavenport's fork"
arch=('i686' 'x86_64')
url="http://github.com/DaveDavenport/simpleswitcher"
license=('MIT')
conflicts=('simpleswitcher-git')
depends=('libx11' 'libxft' 'freetype2' 'libxdg-basedir')
makedepends=('git' 'clang')
provides=('rofi')
source=("git://github.com/DaveDavenport/simpleswitcher.git")
md5sums=('SKIP')

pkgver() {
  cd "$_gitname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "$srcdir/$_gitname"
  make
}

package() {
  cd "$srcdir/$_gitname"
  make DESTDIR="$pkgdir" install
}
