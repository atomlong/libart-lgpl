#!/hint/bash
# Maintainer : bartus <arch-user-repo[at]bartus.33mail.com>
# Contributor : Jan de Groot <jgc@archlinux.org>
# shellcheck disable=SC2034,SC2154 #unused uninitialized variable
# shellcheck disable=SC2164 #cd safe

pkgname=libart-lgpl
pkgver=2.3.21
pkgrel=5
pkgdesc="A library for high-performance 2D graphics"
url="https://www.levien.com/libart/"
arch=('x86_64' 'arm' 'armv6h' 'armv7h' 'aarch64')
license=('LGPL')
source=("https://download.gnome.org/sources/libart_lgpl/2.3/libart_lgpl-${pkgver}.tar.bz2"
		config.guess
        config.sub)
sha256sums=('fdc11e74c10fc9ffe4188537e2b370c0abacca7d89021d4d303afdf7fd7476fa'
			'7d1e3c79b86de601c3a0457855ab854dffd15163f53c91edac54a7be2e9c931b'
			'0c6489c65150773a2a94eebaa794b079e74a403b50b48d5adb69fc6cd14f4810')

prepare() {
  cd "${srcdir}/libart_lgpl-${pkgver}"
  cp -vf ${srcdir}/config.guess	${srcdir}/libart_lgpl-${pkgver}
  cp -vf ${srcdir}/config.sub	${srcdir}/libart_lgpl-${pkgver}
}

build() {
  cd "${srcdir}/libart_lgpl-${pkgver}"
  ./configure --prefix=/usr --disable-static
  make
}

package() {
  cd "${srcdir}/libart_lgpl-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
