# Maintainer: Your Name <youremail@domain.com>
pkgname=git-ghost-git
pkgver=r337.9c3a136
pkgrel=1
pkgdesc=""
arch=("x86_64")
url=""
license=('unknown')
groups=()
depends=()
makedepends=('git' 'go')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
replaces=()
backup=()
options=()
install=
source=('git+https://github.com/pfnet-research/git-ghost')
noextract=()
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/${pkgname%-git}"
  mkdir -p build/

  # Git, no tags available
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  # Install git-ghost
  cd "$srcdir/${pkgname%-git}"
  make OUTDIR=build build
}

package() {
  cd "$srcdir/${pkgname%-git}"
  install -Dm755 build/${pkgname%-git} "$pkgdir"/usr/bin/${pkgname%-git}
}
