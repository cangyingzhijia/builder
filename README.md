# 一、使用说明：
* 1、安装blade构建环境:
  * 1) 执行blade下面的install脚本进行安装： blade/install 
      说明： 本脚本会在$HOME/bin下面添加一些blade支撑工具(blade、bladefunctions、genlibbuild、lsnobuild、lsrc、merge-static-libs)的软连接,
             同时会在$HOME/.vim下面添加blade语法高亮、indent的vim插件
  * 2) source $HOME/.bash_profile
 
* 2、执行完上面的两步骤后blade就安装完毕了，后续就可以在指定的BLADE_ROOT下面开始使用blade进行build了
    blade build ...
 
# 二、目录结构
 * blade: blade构建工具源码及辅助工具
 
 * ccache: blade使用的编译cache工具,ccache是一个强大的编译结果cache工具，
        有了它以后就可以再构建过程中不需要重复编译，大大加快了编译过程，在构建过程中会在$BLADE_ROOT_DIR下面产生一个ccache-dir目录，
        用于存放cache结果。如果对ccache感兴趣可以访问https://ccache.samba.org/ 
 
 * scons: blade依赖的构建工具，blade其实只是生成scons脚本，后续的构建过程由scons进行。
        scons可以单独安装，但是为了便利这里把scons和blade集成在一起。
        对scons的进一步了解请访问http://www.scons.org/
