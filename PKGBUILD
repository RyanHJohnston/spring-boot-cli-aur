# Maintainer: Ryan H. Johnston <ryanhjohnston1204@gmail.com>
# Contributor: Miroslav Koškár <http://mkoskar.com/>

pkgname=spring-boot-cli
pkgver=3.1.0
pkgrel=1
pkgdesc='Spring Boot CLI'
url=https://spring.io/projects/spring-boot
license=(Apache)
arch=(any)
depends=(bash 'java-environment>=8')

# source=("https://repo.spring.io/release/org/springframework/boot/spring-boot-cli/$pkgver/spring-boot-cli-$pkgver-bin.tar.gz")

# Gonna try to update the package
source=("https://repo.maven.apache.org/maven2/org/springframework/boot/spring-boot-cli/$pkgver/spring-boot-cli-$pkgver-bin.tar.gz")

md5sums=('3e0aa39158918e19b90a8660936e42f7')

package() {
    cd spring-"$pkgver"

    install -d "$pkgdir/opt/$pkgname"
    cp -dr --preserve=mode -t "$pkgdir/opt/$pkgname" bin lib legal
    rm "$pkgdir/opt/$pkgname/bin/spring.bat"

    install -d "$pkgdir"/usr/bin
    ln -s /opt/"$pkgname"/bin/spring "$pkgdir"/usr/bin/spring

    install -D -m644 -t "$pkgdir"/usr/share/bash-completion/completions shell-completion/bash/spring
    install -D -m644 -t "$pkgdir"/usr/share/zsh/site-functions shell-completion/zsh/_spring
}


