pkgname=wgns
pkgver=0.1
pkgrel=1
pkgdesc='Framework to manage Linux network namespaces with a Wireguard interface as only way of accessing the Internet'
arch=(
	any
)
url=https://github.com/kalrish/wgns
license=(
	'GPL'
)
groups=(
)
depends=(
	'bash>=5.1.012'
	'iproute2>=5.15.0'
)
makedepends=(
	'git'
)
provides=(
)
conflicts=(
)
replaces=(
)
backup=(
)
options=(
)
install=
source=(
	'sources::git+https://github.com/kalrish/wgns.git#branch=main'
)
noextract=(
)
md5sums=(
	'SKIP'
)

build()
{
	cd sources

	echo '#!/usr/bin/bash' > wgns
	tee --append wgns < wgns.sh > /dev/null
}

package()
{
	cd sources

	install \
		-D \
		--target-directory "${pkgdir}/usr/bin" \
		--mode u=rwx,go=rx \
		-- \
		wgns
	install \
		-D \
		--target-directory "${pkgdir}/usr/lib/systemd/system" \
		--mode u=rw,go=r \
		-- \
		wgns@.service
}
