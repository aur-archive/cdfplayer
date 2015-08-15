# Maintainer: Christian Bühler <christian@cbuehler.de>
# Contributor: kevku <kevku@gmx.com>
pkgname=cdfplayer
pkgver=9.0.1
pkgrel=1
pkgdesc="Wolfram CDF Player"
arch=('x86_64' 'i686')
url="http://www.wolfram.com/cdf-player/"
license=('proprietary')
depends=('unixodbc')
if [[ "$CARCH" == 'i686' ]]; then
  depends+=('alsa-lib' 'mesa' 'libxmu' 'glib2' 'libxi' 'libxrender')
else
  depends+=('lib32'-{'alsa-lib','mesa','libxmu','glib2','libxi','libxrender'})
fi
options=("!strip")
source=("CDFPlayer_${pkgver}_LINUX.sh::file://CDFPlayer_${pkgver}_LINUX.sh")
md5sums=('c046cedf270ed7861240567fb2792558')
PKGEXT=".pkg.tar"

package() {
  chmod +x ${srcdir}/CDFPlayer_${pkgver}_LINUX.sh
  ${srcdir}/CDFPlayer_${pkgver}_LINUX.sh --nox11 -- -auto -targetdir=$pkgdir/opt/Wolfram/CDFPlayer/9.0 -execdir=$pkgdir/usr/bin
  cd $pkgdir/usr/bin
  rm *
  ln -s /opt/Wolfram/CDFPlayer/9.0/Executables/wolframcdfplayer
  ln -s /opt/Wolfram/CDFPlayer/9.0/Executables/WolframCDFPlayer
}

# vim:set ts=2 sw=2 et:
