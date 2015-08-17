# Maintainer: lilydjwg <lilydjwg@gmail.com>
pkgname=python-you-get-git
pkgrel=1
pkgdesc="A YouTube/Youku/Sohu/Tudou/QQ/Sina/PPTV/Xiami/YouTube/Vimeo/ifeng/AcFun/bilibili/CNTV/... video downloader written in Python 3."
arch=('any')
url="http://www.soimort.org/you-get/"
license=('MIT')
depends=('python' 'python-distribute')
source=("git://github.com/soimort/you-get.git")
md5sums=(SKIP)
pkgver=0.3.27.20140214

_repo_name=you-get

pkgver() {
  cd "$srcdir/$_repo_name"
  echo $(python -c "exec(compile(open('src/you_get/version.py').read(), 'version.py', 'exec')); print(__version__)").$(git log -1 --format='%ad' --date=short|tr -d '-')
  # git log -1 --format="%cd" --date=short | tr -d -
}

build() {
  cd "$srcdir/$_repo_name"

  msg "GIT checkout done or server timeout"
  msg "Starting make..."

  python setup.py build
}

package() {
  cd "$srcdir/$_repo_name"
  python setup.py install --root=$pkgdir/ --optimize=1
}
