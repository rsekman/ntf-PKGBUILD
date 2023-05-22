# Maintainer: Robin Ekman < robin.seth.ekman [at] gmail [dot] com >

_pkgname=ntf
pkgname=${_pkgname}-git
pkgver=v1.0.1.r3.gd52a786
pkgrel=1
pkgdesc="Brings notification to your shell"
url='https://github.com/hrntknr/ntf'
arch=('any')
license=('GPL3')
depends=()
makedepends=(
    'go'
)
source=(
    'git+https://github.com/hrntknr/ntf.git'
)
sha256sums=(
    'SKIP'
)

provides=("${pkgname}")

pkgver() {
    cd "${_pkgname}"

    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
	cd "${_pkgname}"

	go build -ldflags "-s -w"
}

package() {
	cd "${_pkgname}"

    install -Dm755 -t "${pkgdir}/usr/bin" ./ntf
}
