# Maintainer: Aleksey Smirnov <debugger94 [at] gmail [dot] com>
pkgname=byedpi-bin
pkgver=0.15.0
pkgrel=1
pkgdesc="local SOCKS proxy server. Implementation of some DPI bypass methods."
arch=('x86_64' 'aarch64' 'armv7h')
url="https://github.com/hufrea/byedpi"
license=('MIT')
#groups=()
#depends=()
#makedepends=()
#optdepends=()
provides=(${pkgname%-bin})
conflicts=(${pkgname%-bin})
#replaces=()
backup=(etc/byedpi/options)
options=(!debug)
#install=
#changelog=

_ver_st=${pkgver/%.0/}   # strip trailing zero (0.10.0 -> 0.10)
_ver_slt=${_ver_st/#0./} # strip leading and trailing zeros (0.10.0 -> 10)

source_x86_64=("$url/releases/download/v$_ver_st/byedpi-$_ver_slt-x86_64.tar.gz"
               "$url/raw/main/LICENSE"
               byedpi.service
               #ciadpi-completion.bash
               byedpi_options)
source_aarch64=("$url/releases/download/v$_ver_st/byedpi-$_ver_slt-aarch64.tar.gz"
                "$url/raw/main/LICENSE"
                byedpi.service
                #ciadpi-completion.bash
                byedpi_options)
source_armv7h=("$url/releases/download/v$_ver_st/byedpi-$_ver_slt-armv7l.tar.gz"
                "$url/raw/main/LICENSE"
                byedpi.service
                #ciadpi-completion.bash
                byedpi_options)
#noextract=()
sha256sums_x86_64=('b25027c7795815f9de8a792e4c3900a6cb8026a57d58033d0f2896d574c01c90'
                   '18c854c6c25dffefe4b522cf1bdf5d15278a25ca785948258bddb94393f575eb'
                   '36cb5decab3e2a5e80ae8b7511fab59defacd7b627457463307497b93074adaf'
                   '252beec797a394de02499404e5e113c784a12562d26c761d0737321be6f44d35')
sha256sums_aarch64=('aaaab34c58b26ef3b5370093976af7bba9ad2ef149e571054d40522c242f3554'
                    '18c854c6c25dffefe4b522cf1bdf5d15278a25ca785948258bddb94393f575eb'
                    '36cb5decab3e2a5e80ae8b7511fab59defacd7b627457463307497b93074adaf'
                    '252beec797a394de02499404e5e113c784a12562d26c761d0737321be6f44d35')
sha256sums_armv7h=('e766cbd301bfb78aa25f3da42468033dcdacc14b8b5fccaaf4f361fa5a81976e'
                   '18c854c6c25dffefe4b522cf1bdf5d15278a25ca785948258bddb94393f575eb'
                   '36cb5decab3e2a5e80ae8b7511fab59defacd7b627457463307497b93074adaf'
                   '252beec797a394de02499404e5e113c784a12562d26c761d0737321be6f44d35')

package() {
  cd $srcdir
  
  install -Dm 755 "$srcdir"/ciadpi-*  "$pkgdir"/usr/bin/ciadpi
  install -Dm 644 "$srcdir"/byedpi.service -t "$pkgdir"/usr/lib/systemd/system
  install -Dm 644 "$srcdir"/byedpi_options "$pkgdir"/etc/byedpi/options
  install -Dm 644 "$srcdir"/LICENSE -t "$pkgdir"/usr/share/licenses/byedpi
  #install -Dm 644 "$srcdir"/ciadpi-completion.bash "$pkgdir"/usr/share/bash-completion/completions/ciadpi
}

