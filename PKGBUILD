# Maintainer: <qqqqqqqqq9 at web dot de>
pkgname=opera-mini
pkgver=8.0.35158
pkgrel=1
arch=('any')
pkgdesc="A web browser optimized for small bandwidth"
url="http://www.opera.com/de/mobile"
license=('custom')
depends=('microemulator' 'desktop-file-utils')
install=${pkgname}.install
source=('opera-mini.desktop'
	'opera-mini.launcher'
  'LICENSE'
#   The jad-files is different on every download. However it does not seem to be neccessary.
#   "http://mini.opera.com/download-7/opera-mini-$pkgver-advanced-en.jad"
  "http://mini.opera.com/download-7/opera-mini-$pkgver-advanced-en.jar")
noextract=('opera-mini-$pkgver-advanced-en.jar' 'opera-mini-$pkgver-advanced-en.jad')
md5sums=('8612dee60e9087b69499a3a39e6deacb'
         '4e6864e54e5a459ac5bd10b34192bb21'
         '80b2d25d76d6bc19b83fc71021a80c48'
         '0f9f80729016f593e53a4f1819fc3792')
package() {
  cd $srcdir
  mkdir -p "$pkgdir"/usr/share/java/microemulator/apps/ "$pkgdir"/usr/share/applications/
  install -Dm644 opera-mini-$pkgver-advanced-en.ja* "$pkgdir"/usr/share/java/microemulator/apps/
  sed -e "s/latest/$pkgver/" -i opera-mini.launcher
  install -Dm755 opera-mini.launcher "$pkgdir"/usr/bin/opera-mini
  install -Dm644 opera-mini.desktop  "$pkgdir"/usr/share/applications/
  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
