# Maintainer: Jose C.

pkgname=jetbrains-webstorm
pkgver='2021.2.3'
pkgrel=1
pkgdesc='integrated development environment for JavaScript and related technologies'
arch=('x86_64')
options=('!strip' 'staticlibs')
url='https://www.jetbrains.com/webstorm/'
license=('Commercial')
optdepends=()
provides=('webstorm')
conflicts=('webstorm')

_filename="WebStorm-${pkgver}.tar.gz"
_filextract="WebStorm-212.5457.55"

source=("https://download.jetbrains.com/webstorm/WebStorm-2021.2.3.tar.gz" "${pkgname}.desktop")

sha256sums=( 'aefdd1ad4eac642a3f26cd480f1ee1cf2c8aecf043131b1833ad7af265e8e934'
	'5ca988c8bd990590574d079ec95d3da8ecec693bf78bb49561b9f7a5c7c08cb0') 

package() {
	cd "${srcdir}"

	#Create directories with permission rwxr-xr-x
	install -d -m755 "${pkgdir}/usr/share" 
	install -d -m755 "${pkgdir}/usr/bin"
	install -d -m755 "${pkgdir}/usr/share/applications"

	#Copy files to pkg destination
	cp -a "${_filextract}" "${pkgdir}/usr/share/${pkgname}"
	chown -R root:root "${pkgdir}/usr/share/${pkgname}"

	ln -s "/usr/share/jetbrains/webstorm/bin/webstorm.sh" "${pkgdir}/usr/bin/webstorm"
  install -m644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications"

}
