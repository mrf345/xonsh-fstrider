# Maintainer: Mohamed Feddad <mrf345@gmail.com>

pkgname=xonsh-fstrider-git
pkgver=r127.3e98dce
pkgrel=1
pkgdesc="fstrider is an intuitive and fast file system navigator for xonsh terminal"
url="https://github.com/mrf345/xonsh-fstrider"
arch=('any')
license=('MIT')
source=("git+$url")
depends=('xonsh' 'python')
makedepends=('git' 'python-setuptools' 'python-build' 'python-installer' 'python-wheel' 'python-poetry')

sha256sums=('SKIP')
provides=("xonsh-fstrider")

pkgver() {
    cd "${srcdir}/${pkgname%-git}"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    cd "${srcdir}/${pkgname%-git}"
    python -m build --wheel --no-isolation
}

package() {
    cd "${srcdir}/${pkgname%-git}"
    python -m installer --destdir="$pkgdir" dist/*.whl
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
