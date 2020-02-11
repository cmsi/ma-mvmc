# ma-mvmc

## How to prepare source files for mvmc package

1. ソースファイルの準備 (ホスト上で)

        VERSION=1.1.1
        cd $HOME/vagrant/data/src
	rm -rf mVMC-${VERSION}.tar.gz mVMC-${VERSION} mvmc_${VERSION}
        wget https://github.com/issp-center-dev/mVMC/releases/download/v${VERSION}/mVMC-${VERSION}.tar.gz
	tar zxvf mVMC-${VERSION}.tar.gz
	mv mVMC mvmc_${VERSION}
        rm -rf mvmc_${VERSION}/.git
        find mvmc_${VERSION} -name '._*' | xargs rm -f
        find mvmc_${VERSION} -name '.gitignore' | xargs rm -f
	tar zcvf mvmc_${VERSION}.orig.tar.gz mvmc_${VERSION}
	rm -rf mvmc_${VERSION} mVMC-${VERSION}.tar.gz
