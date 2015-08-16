pkgname=minitube-git
pkgver=2.3.1
pkgrel=1
epoch=1
pkgdesc="A native YouTube client in QT. Watch YouTube videos without Flash Player."
url="http://flavio.tordini.org/minitube"
license="GPL"
arch=('any')
depends=('phonon' 'qt4')
makedepends=('git')
optdepends=('phonon-xine: for xine backend'
            'phonon-gstreamer: for gstreamer backend'
            'gstreamer0.10-plugins: to get all videos to play with phonon-gstreamer'
            'phonon-mplayer-git: for mplayer backend (from AUR)'
            'phonon-vlc-git: for vlc backend (from AUR)')
provides=('minitube')
conflicts=('minitube')
install=minitube.install
source=(git://gitorious.org/minitube/minitube.git)
md5sums=(SKIP)

pkgver() {
  cd minitube
  git describe --tags | sed "s/-/./g"
}

build() {
  cd minitube
  qmake-qt4 PREFIX="/usr"
}

package() {
  cd minitube
  make INSTALL_ROOT="$pkgdir/" install
}