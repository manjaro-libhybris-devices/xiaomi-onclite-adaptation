# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=xiaomi-onclite-adaptation
provides=(halium9-post-install)
conflicts=(halium9-post-install)
pkgver=1$(date +%y%m%d)
pkgrel=1
pkgdesc="Manjaro libhybris adaptation for xiaomi onclite"
arch=('any')
url="https://github.com/manjaro-libhybris-devices/xiaomi-onclite-adaptation"
license=('GPL')
depends=('gzip' 'glibc-locales' 'wget' 'systemd')
makedepends=('git')
source=("xiaomi-onclite-adaptation::git+https://github.com/manjaro-libhybris-devices/xiaomi-onclite-adaptation.git")
install=$pkgname.install
md5sums=('SKIP')

package() {
    mv "${srcdir}/xiaomi-onclite-adaptation/xiaomi-onclite-adaptation.sh" "${srcdir}/xiaomi-onclite-adaptation/xiaomi-onclite-adaptation"

    mkdir -p "${pkgdir}/usr/bin/"
    install -Dm755 "${srcdir}/xiaomi-onclite-adaptation/xiaomi-onclite-adaptation" -t "${pkgdir}/usr/bin/"
    mkdir -p "${pkgdir}/usr/lib/systemd/system/"
    install -Dm644 "${srcdir}/xiaomi-onclite-adaptation/xiaomi-onclite-adaptation.service" -t "${pkgdir}/usr/lib/systemd/system/"
    mkdir -p "${pkgdir}/usr/lib/sysusers.d/"
    install -Dm644 "${srcdir}/xiaomi-onclite-adaptation/android.conf" -t "${pkgdir}/usr/lib/sysusers.d/"

    mkdir -p ${pkgdir}/etc/phosh/
    install -Dm644 "${srcdir}/xiaomi-onclite-adaptation/phoc.ini" -t "${pkgdir}/etc/phosh/"
    mkdir -p "${pkgdir}/etc/udev/rules.d/"
    cp -r "${srcdir}/xiaomi-onclite-adaptation/70-onclite.rules" -t "${pkgdir}/etc/udev/rules.d/"

    mkdir -p "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-onclite-adaptation/boot.img" -t "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-onclite-adaptation/dtbo.img" -t "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-onclite-adaptation/vbmeta.img" -t "${pkgdir}/boot/"

    mkdir -p "${pkgdir}/usr/lib/systemd/system/"
    install -Dm644 "${srcdir}/xiaomi-onclite-adaptation/brightnessperm.service" "${pkgdir}/usr/lib/systemd/system/"
}
