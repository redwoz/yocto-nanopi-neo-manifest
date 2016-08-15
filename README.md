# yocto-nanopi-neo-manifest

curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > repo

chmod a+x repo

sudo mv repo /usr/local/bin/

mkdir yh3

cd yh3

repo init -u git://github.com/redwoz/yocto-nanopi-neo-manifest.git 

repo sync

export TEMPLATECONF=../meta-h3-extras/conf

source ./poky/oe-init-build-env test

bitbake neo-console-image

sudo dd if=./tmp/deploy/images/nanopi-neo/neo-console-image-nanopi-neo.sunxi-sdimg of=/dev/disk/by-id/usb-Generic-_USB3.0_CRW-SD_MS_201006010301-0:1 bs=1024

