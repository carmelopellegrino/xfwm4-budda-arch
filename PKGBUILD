# $Id$
# Maintainer: Carmelo Pellegrino <carmelo dot pellegrino at gmail dot com>

pkgname=xfwm4-budda
_pkgname=${pkgname%-*}
pkgver=4.12.0
pkgrel=2
pkgdesc="Xfce 4 window manager with customizable move-to-workspace behaviour."
branch_name="change_workspace_on_shortcut_window_move"
arch=('i686' 'x86_64')
url="https://github.com/carmelopellegrino/xfwm/"
license=('GPL2')
groups=('xfce4')
depends=('libxfce4ui' 'libwnck' 'hicolor-icon-theme')
optdepends=()
makedepends=('intltool')
provides=('xfwm4=$pkgver')
conflicts=('xfwm4' 'xfwm4-titless+')
options=('!libtool')
install=xfwm4.install
source=("$pkgname-$pkgver.tar.gz::https://github.com/carmelopellegrino/xfwm/archive/${branch_name}.tar.gz")
sha256sums=('695cfc59eddcdf8baee70f4aedec1d24fdf9ac99be10ca03c7725eb43c61e83a')

build() {
  cd "$srcdir/xfwm-change_workspace_on_shortcut_window_move"

    ./autogen.sh \
    --prefix=/usr \
    --sysconfdir=/etc \
    --libexecdir=/usr/lib \
    --localstatedir=/var \
    --disable-static \
    --enable-startup-notification \
    --enable-randr \
    --enable-compositor \
    --enable-xsync \
    --enable-debug=minimal

  make
}

package() {
  cd "$srcdir/xfwm-change_workspace_on_shortcut_window_move"
  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
