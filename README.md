# mellow-fly-fast-toolchanger
mellow fly fast系统下安装 toolchanger插件最容易的方法


在ssh 链接klipper 直接复制/粘贴 就可以了


###第一步
git clone https://github.com/viesturz/klipper-toolchanger.git /data/klipper-toolchanger
cp -ri /data/klipper-toolchanger/klipper/extras/* /data/klipper/klippy/extras/


###第二步
cd /data
git clone https://github.com/viesturz/tapchanger.git --no-checkout --depth 1 --filter=blob:none
cd tapchanger
git sparse-checkout init --cone
git sparse-checkout set Klipper
git checkout
ln -s /data/tapchanger/Klipper/config-example /usr/share/printer_data/config/tapchanger


###第三步 ———nternal error during connect: HomingViaProbeHelper._init__O takes 4 positional arguments but 5 were given———如果出现这个报错请用这条命令
rm -rf /data/klipper
cd && git clone https://cnb.cool/3dmellow/public/klipper -b dev-flyos /data/klipper
cp -ri /data/klipper-toolchanger/klipper/extras/* /data/klipper/klippy/extras/
