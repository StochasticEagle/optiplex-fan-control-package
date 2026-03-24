# Maintainer: Aaron Stone <https://gitlab.com/StochasticEagle>
pkgname=optiplex-fan-control
pkgver=1.0.0
pkgrel=1
pkgdesc="Linear fan control daemon and BIOS bypass for Dell OptiPlex SFF series"
arch=('x86_64')
url="https://gitlab.com/StochasticEagle/optiplex-fan-control"
source=("$pkgname-$pkgver.tar.gz::$url/-/archive/v$pkgver/$pkgname-v$pkgver.tar.gz")
license=('MIT')
depends=('gcc-libs' 'bash' 'msr-tools' 'lm_sensors' 'glibc')
install=optiplex-fan-control.install
sha256sums=('26e4f731dc202cffdd5935d0b5b575e382cef74c6b684edfdc56e06177cec951')

build() {
  # Use a wildcard to enter the directory created by the GitLab archive
  cd "$srcdir/$pkgname-v$pkgver"
  make
}

package() {
  cd "$srcdir/$pkgname-v$pkgver"

  # 1. Install Binaries to /usr/bin
  install -Dm755 dell-bios-fan-control "$pkgdir/usr/bin/dell-bios-fan-control"
  install -Dm755 optiplex-fan-daemon "$pkgdir/usr/bin/optiplex-fan-daemon"

  # 2. Configuration (User Editable in /etc)
  install -Dm644 optiplex-fan-config "$pkgdir/etc/optiplex-fan-config"

  # 3. Systemd Service
  install -Dm644 optiplex-fan.service "$pkgdir/usr/lib/systemd/system/optiplex-fan.service"
}
