#this sources cloned from Kunbus
  Revoulution Pi 용 커스텀 이미지 제작.

  Greengrass 환경을 셋업하기 위해서는 Python3.7 이상의 버전 및 각종 templates 대치 필요.

#making_gg_env.sh
  revolution pi 및 raspberry pi를 위한 greengrass 환경 셋업 script
  Python3.7.2 버전 자동 인스톨 빌드(ssl import error 해결)
  hardlink, symlink protection 및 cgroup enable, ggc group & ggc user adding


Create custom images for Revolution Pi

Intended usage:

* Download Raspbian image, works with both desktop and lite images:
  curl -O http://downloads.raspberrypi.org/raspbian/images/raspbian-2019-04-09/2019-04-08-raspbian-stretch.zip
  curl -O http://downloads.raspberrypi.org/raspbian_lite/images/raspbian_lite-2019-04-09/2019-04-08-raspbian-stretch-lite.zip
  unzip *-raspbian-*.zip
  rm *-raspbian-*.zip

* Customize for Revolution Pi
  (requires root, an armhf system (RasPi or VM) and Internet connectivity;
  to cross-build, apt-get install qemu-user-static binfmt-support;
  custom packages can be placed in debs-to-install/):
  customize_image.sh <raspbian-image>

* Collect sources on a physical medium for GPL compliance
  (requires root and Internet connectivity):
  collect_sources.sh <raspbian-image> /media/usbstick
