#!/bin/bash

# Adapted from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-freetype-py/discussions>

pkgname=fontdiffenator
pkgver=0.9.12
pkgrel=5
pkgdesc='Font regression tester for Google Fonts'
arch=(any)
url="https://github.com/googlefonts/$pkgname"
license=(Apache)
depends=(
  "python"
  "python-fonttools"
  "python-pillow"
  "cairo"
  "python-uharfbuzz"
  "python-freetype-py"
)
makedepends=(
  "python-setuptools"
)

source=(
  "https://files.pythonhosted.org/packages/source/${pkgname::1}/$pkgname/$pkgname-$pkgver.tar.gz"
)
sha512sums=(
  "3fadb150fe6579a6de091ca245d20a4bf2d821a0261b2f2994ead075e417cfcbecdf58a1c79654ba98b3a91bc479c771976acaff16e3048c48a1d010cba0647a"
)

build() {

  cd "$pkgname-$pkgver"

  python setup.py build
}

package() {

  cd "$pkgname-$pkgver"

  python setup.py install --root="$pkgdir" --optimize=1 --skip-build
}
