# Contributor: feilen <feilen1000@gmail.com>

pkgname=octoprint-git
pkgver=1.0.0.rc1.r3.gb282a18
pkgrel=1
pkgdesc="OctoPrint provides a responsive web interface for controlling a 3D printer (RepRap, Ultimaker, ...)"
arch=('i686' 'x86_64' 'armv6' 'armv6h')
license=('GPL')
depends=( 'python2-flask' 'python2-numpy' 'python2-pyserial' 'python2-tornado' 'python2-tornadio2' 'python2-yaml' 'python2-flask-login' 'python2-flask-principal' 'python2-netaddr' 'python2-blinker' 'python2-sockjs-tornado-git' )
makedepends=( 'git' )
# No package for MJPG-Streamer yet. Perhaps make one?
optdepends=( 
	'ffmpeg: timelapse support' )
provides=( 'octoprint' )
conflicts=( 'octoprint' )
source=(
octoprint.service
config.yaml
run
)
md5sums=('SKIP' 'SKIP' 'SKIP')

package() {
	mkdir -p ${pkgdir}/usr/share/octoprint/

	cp -a ${srcdir}/octoprint/* ${pkgdir}/usr/share/octoprint/

	install -D -m644 ${srcdir}/config.yaml ${pkgdir}/etc/octoprint.yaml
	install -D -m755 ${srcdir}/run ${pkgdir}/usr/bin/octoprint
	install -D -m644 ${srcdir}/octoprint.service ${pkgdir}/usr/lib/systemd/system/octoprint.service
}
