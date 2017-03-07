# base

#目录说明
bin:      存放动态库 或 执行文件
build:    编译各平台的版本
make:     makefile脚本的存
include:  导出头文件
lib:      第三方库
pack:     打包后版本
platform: 对各地平台编译参数及工具链配置  
project:  对单个项目编译参数配置 
src:      源代码
test:     测试工具及脚本
tools:    各平台工具链或软链接

# 如何编译armeabi工程
(1) base/tools/armeabi-android 目录下
  ln -s /tools/toolchain/android-ndk-r10d android-ndk-r10d
(2) base/platform/armeabi-android/make 目录下
   修改cmd.mk flag.mk ,  如果不是 android-ndk-r10d NDK，需要改成对应名字的NDK
(3)  base/build 目录下
    #以编译release版本为例
    make armeabi-android config=release all-project


# 如何编译windows