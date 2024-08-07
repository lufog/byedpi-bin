# Maintainer: Aleksey Smirnov <debugger94@gmail.com>
pkgname=byedpi-bin
pkgver=0.12.0
pkgrel=1
pkgdesc="local SOCKS proxy server. Implementation of some DPI bypass methods."
arch=('x86_64' 'aarch64' 'armv7h')
url="https://github.com/hufrea/byedpi"
license=('MIT')
#groups=()
#depends=()
#makedepends=()
#optdepends=()
#provides=()
#conflicts=()
#replaces=()
backup=(etc/byedpi/options)
#options=()
#install=
#changelog=

_ver_st=${pkgver/%.0/}   # strip trailing zero (0.10.0 -> 0.10)
_ver_slt=${_ver_st/#0./} # strip leading and trailing zeros (0.10.0 -> 10)

source_x86_64=("https://github.com/hufrea/byedpi/releases/download/v$_ver_st/byedpi-$_ver_slt-x86_64.tar.gz"
               byedpi.service
               #ciadpi-completion.bash
               byedpi_options)
source_aarch64=("https://github.com/hufrea/byedpi/releases/download/v$_ver_st/byedpi-$_ver_slt-aarch64.tar.gz"
                byedpi.service
                #ciadpi-completion.bash
                byedpi_options)
source_armv7h=("https://github.com/hufrea/byedpi/releases/download/v$_ver_st/byedpi-$_ver_slt-armv7l.tar.gz"
                byedpi.service
                #ciadpi-completion.bash
                byedpi_options)
#noextract=()
sha256sums_x86_64=('20abf3ec48798b1a17de55b9ca8c70a4ac270e8bf58725d45d680de8efb4c40f'
                   '33a613b4849a447a994ea49311a9355fd7a6f09dd9fdfa6d4d3d5ba773cce3a2'
                   'a3cef82b292db120648ecfdc81e5a67ece4b78cd4ec1edf8ac18c58ad6461d63')
sha256sums_aarch64=('1508de12fe302d6cec92173c6ab18196716e8650ccfd70bde21df18d3822492d'
                    '33a613b4849a447a994ea49311a9355fd7a6f09dd9fdfa6d4d3d5ba773cce3a2'
                    'a3cef82b292db120648ecfdc81e5a67ece4b78cd4ec1edf8ac18c58ad6461d63')
sha256sums_armv7h=('38393ed4b4e6022e9dc1e954008205f1fb570c39776418f5261e30c8a5412d6a'
                   '33a613b4849a447a994ea49311a9355fd7a6f09dd9fdfa6d4d3d5ba773cce3a2'
                   'a3cef82b292db120648ecfdc81e5a67ece4b78cd4ec1edf8ac18c58ad6461d63')

package() {
  cd $srcdir
  
  install -Dm 755 "$srcdir"/ciadpi-*  "$pkgdir"/usr/bin/ciadpi
  install -Dm 644 "$srcdir"/byedpi.service -t "$pkgdir"/usr/lib/systemd/system
  #install -Dm 644 "$srcdir"/ciadpi-completion.bash "$pkgdir"/usr/share/bash-completion/completions/ciadpi
  install -Dm 644 "$srcdir"/byedpi_options "$pkgdir"/etc/byedpi/options
}

