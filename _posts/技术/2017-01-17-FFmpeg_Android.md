ffmpeg 3.2 ndk9d linux32  android 动态库生成过程 [东软镜像](http://mirrors.neusoft.edu.cn/)<br> 

* git clone https://git.ffmpeg.org/ffmpeg.git ffmpeg 下载NDK  http://www.androiddevtools.cn/ 
* 更改 configure 文件
  将
  
```
  SLIBNAME_WITH_MAJOR='$(SLIBNAME).$(LIBMAJOR)'
  LIB_INSTALL_EXTRA_CMD='$$(RANLIB)"$(LIBDIR)/$(LIBNAME)"'
  SLIB_INSTALL_NAME='$(SLIBNAME_WITH_VERSION)'
  SLIB_INSTALL_LINKS='$(SLIBNAME_WITH_MAJOR)$(SLIBNAME)'
```

  改为
  
```
  SLIBNAME_WITH_MAJOR='$(SLIBPREF)$(FULLNAME)-$(LIBMAJOR)$(SLIBSUF)'
  LIB_INSTALL_EXTRA_CMD='$$(RANLIB)"$(LIBDIR)/$(LIBNAME)"'
  SLIB_INSTALL_NAME='$(SLIBNAME_WITH_MAJOR)'
  SLIB_INSTALL_LINKS='$(SLIBNAME)'   
```

* 编写build_android.sh 相关变量按照各自的环境修改
* 执行 ./build_android.sh && make && make install   然后会生成动态库文件
