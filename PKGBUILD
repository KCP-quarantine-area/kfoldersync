pkgname=kfoldersync
pkgver=3.2.0
pkgrel=1
pkgdesc="Folder synchronization and backup tool for KDE"
arch=('x86_64')
url='http://kde-apps.org/content/show.php/KFolderSync?content=164092'
license=('GPL')
depends=('kcoreaddons' 'kdbusaddons' 'ki18n' 'kio' 'knotifications' 'kxmlgui' 'hicolor-icon-theme')
makedepends=('cmake' 'extra-cmake-modules' 'gettext')
source=("https://dl.opendesktop.org/api/files/download/id/1466630097/164092-${pkgname}-${pkgver}.tar.xz")
md5sums=('77c59d1ab569682a5801e4202416d671')


prepare() {
    cd "$srcdir/${pkgname}-${pkgver}"
    mkdir build
}

build() {
    cd "${pkgname}-${pkgver}/build"
    cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release ..
    make
}

package() {
    cd "${pkgname}-${pkgver}/build"
    make DESTDIR="${pkgdir}/" install
}
