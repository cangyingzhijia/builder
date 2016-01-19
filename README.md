# builder简介
 一个集成blade、ccache、cpplint、scons的构建环境，直接下载下来就可以使用，省却各种依赖环境的配置

# 使用说明
1.安装blade构建环境:
   1) 执行blade下面的install脚本进行安装： blade/install 
      说明： 本脚本会在$HOME/bin下面添加一些blade支撑工具(blade、bladefunctions、genlibbuild、lsnobuild、lsrc、merge-static-libs)的软连接,
             同时会在$HOME/.vim下面添加blade语法高亮、indent的vim插件
  * 2) source $HOME/.bash_profile
 
2. 执行完上面的两步骤后blade就安装完毕了，后续就可以在指定的BLADE_ROOT下面开始使用blade进行build了
    blade build ...
 
# 目录结构
## blade
 blade 是一个现代构建系统，期望的目标是强大而好用，把程序员从构建的繁琐中解放出来。
 对blade的进一步了解请访问:https://github.com/chen3feng/typhoon-blade
 
## ccache
 ccache（“compiler cache”的缩写）是一个编译器缓存，该工具会高速缓存编译生成的信息，
 并在编译的特定部分使用高速缓存的信息， 比如头文件，这样就节省了通常使用 cpp 解析这些信息所需要的时间。
 blade使用的编译cache工具,ccache是一个强大的编译结果cache工具，
 有了它以后就可以再构建过程中不需要重复编译，大大加快了编译过程，在构建过程中会在$BLADE_ROOT_DIR下面产生一个ccache-dir目录，
 用于存放cache结果。如果对ccache感兴趣可以访问:https://ccache.samba.org/ 
 
## scons
 scons是一个Python写的自动化构建工具，从构建这个角度说，它跟GNU make是同一类的工具。
 它是一种改进，并跨平台的gnu make替代工具，其集成功能类似于autoconf/automake。
 scons是一个更简便，更可靠，更高效的编译软件。
 blade依赖的构建工具，blade其实只是生成scons脚本，后续的构建过程由scons进行。
 scons可以单独安装，但是为了便利这里把scons和blade集成在一起。
 对scons的进一步了解请访问:http://www.scons.org/

## cpplint 
 cpplint 是 一个python脚本, google使用它作为自己的C++ 代码规范 检查工具.
 如果你的C++代码遵循的也是 google 的C++代码风格, 那么这个脚本对你来说就非常实用.
 对cpplint的进一步了解请访问:https://github.com/tkruse/cpplint
