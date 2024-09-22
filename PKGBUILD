# Maintainer: Aleksey Smirnov <debugger94 [at] gmail [dot] com>
pkgname=byedpi-bin
pkgver=0.14.1
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
sha256sums_x86_64=(SKIP
                   '18c854c6c25dffefe4b522cf1bdf5d15278a25ca785948258bddb94393f575eb'
                   '33a613b4849a447a994ea49311a9355fd7a6f09dd9fdfa6d4d3d5ba773cce3a2'
                   '826e822fa919ba9725d67c828f858c75121ee2274060400a51686b7586b9ff06')
sha256sums_aarch64=(SKIP
                    '18c854c6c25dffefe4b522cf1bdf5d15278a25ca785948258bddb94393f575eb'
                    '33a613b4849a447a994ea49311a9355fd7a6f09dd9fdfa6d4d3d5ba773cce3a2'
                    '826e822fa919ba9725d67c828f858c75121ee2274060400a51686b7586b9ff06')
sha256sums_armv7h=(SKIP
                   '18c854c6c25dffefe4b522cf1bdf5d15278a25ca785948258bddb94393f575eb'
                   '33a613b4849a447a994ea49311a9355fd7a6f09dd9fdfa6d4d3d5ba773cce3a2'
                   '826e822fa919ba9725d67c828f858c75121ee2274060400a51686b7586b9ff06')

package() {
  cd $srcdir
  
  install -Dm 755 "$srcdir"/ciadpi-*  "$pkgdir"/usr/bin/ciadpi
  install -Dm 644 "$srcdir"/byedpi.service -t "$pkgdir"/usr/lib/systemd/system
  install -Dm 644 "$srcdir"/byedpi_options "$pkgdir"/etc/byedpi/options
  install -Dm 644 "$srcdir"/LICENSE -t "$pkgdir"/usr/share/licenses/byedpi
  #install -Dm 644 "$srcdir"/ciadpi-completion.bash "$pkgdir"/usr/share/bash-completion/completions/ciadpi
}

