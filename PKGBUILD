# Maintainer: Cloudef <mailroxas@gmail.com>

pkgname=swrast-dri
pkgver=9.0.1
pkgrel=1
pkgdesc='Installs swrast dri module from libgl package'
arch=('i686' 'x86_64')
url='http://mesa3d.sourceforge.net'
license=('custom')

# for getting i686 md5sums
# CARCH=i686

# we provide LICENSE, but won't install it
# since it could conflict with libgl package
source=(LICENSE
"libgl-$pkgver-$pkgrel-$CARCH.pkg.tar.xz::http://www.archlinux.org/packages/extra/$CARCH/libgl/download/")
depends=('libdrm>=2.4.31' 'libxxf86vm>=1.1.1' 'libxdamage>=1.1.3' 'expat>=2.0.1' 'libglapi' 'gcc-libs')

case $CARCH in
i686)
   md5sums=('5c65a0fe315dd347e09b1f2826a1df5a'
            'a58b820bf40369a0695f7c1675c26806')
   ;;
x86_64)
   md5sums=('5c65a0fe315dd347e09b1f2826a1df5a'
            '4a9e50238c9653a49322bf3e4b0e87fe')
   ;;
esac

package() {
   cd "$srcdir"
   tar xf "libgl-$pkgver-$pkgrel-$CARCH.pkg.tar.xz"
   install -dm775 "${pkgdir}/usr/lib/xorg/modules/dri"
   install -Dm775 "usr/lib/xorg/modules/dri/swrast_dri.so" "${pkgdir}/usr/lib/xorg/modules/dri/"
}

# vim: set ts=8 sw=3 tw=0 :
