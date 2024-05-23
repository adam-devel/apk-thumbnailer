pkgname=apk-thumbnailer
pkgver=0.0.1
pkgrel=1
pkgdesc="a thumbnailer for android packages"
arch=(x86_64)
depends=('android-sdk-build-tools' 'imagemagick' 'unzip')
source=("apk-thumbnailer")
md5sums=("bdf7800dd79ce6ba98f55c8ab11aff42")

prepare() {
  { # generate a thumbnailer entry file
    echo "[Thumbnailer Entry]"
    echo "TryExec=/usr/bin/$pkgname"
    echo "Exec=/usr/bin/$pkgname %i %o %s"
    echo "MimeType=application/vnd.android.package-archive"
  } >"$pkgname.thumbnailer"
}

package() {
  install -Dm755 apk-thumbnailer -t "$pkgdir/usr/bin/"
  install -Dm644 "$pkgname.thumbnailer" -t "$pkgdir/usr/share/thumbnailers/"
}
