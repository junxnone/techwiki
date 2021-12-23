---
Title | pkg-config
-- | --
Create Date | `2021-10-13T03:36:37Z`
Update Date | `2021-12-23T15:53:27Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/176)

---
# Reference
- [pkg-config 详解](https://blog.csdn.net/newchenxf/article/details/51750239)


# Brief
- pkg-config - `用于获取库相关信息(头文件/库)`
- 查询信息来源
  - /usr/lib/ 下的 `*.pc`
  - `$PKG_CONFIG_PATH` 路径下的 `*.pc`


```
Usage:
  pkg-config [OPTION?]

Help Options:
  -h, --help                              Show help options

Application Options:
  --version                               output version of pkg-config
  --modversion                            output version for package
  --atleast-pkgconfig-version=VERSION     require given version of pkg-config
  --libs                                  output all linker flags
  --static                                output linker flags for static linking
  --short-errors                          print short errors
  --libs-only-l                           output -l flags
  --libs-only-other                       output other libs (e.g. -pthread)
  --libs-only-L                           output -L flags
  --cflags                                output all pre-processor and compiler flags
  --cflags-only-I                         output -I flags
  --cflags-only-other                     output cflags not covered by the cflags-only-I option
  --variable=NAME                         get the value of variable named NAME
  --define-variable=NAME=VALUE            set variable NAME to VALUE
  --exists                                return 0 if the module(s) exist
  --print-variables                       output list of variables defined by the module
  --uninstalled                           return 0 if the uninstalled version of one or more module(s) or their dependencies will be used
  --atleast-version=VERSION               return 0 if the module is at least version VERSION
  --exact-version=VERSION                 return 0 if the module is at exactly version VERSION
  --max-version=VERSION                   return 0 if the module is at no newer than version VERSION
  --list-all                              list all known packages
  --debug                                 show verbose debug information
  --print-errors                          show verbose information about missing or conflicting packages (default unless --exists or --atleast/exact/max-version given on the command line)
  --silence-errors                        be silent about errors (default when --exists or --atleast/exact/max-version given on the command line)
  --errors-to-stdout                      print errors from --print-errors to stdout not stderr
  --print-provides                        print which packages the package provides
  --print-requires                        print which packages the package requires
  --print-requires-private                print which packages the package requires for static linking
  --validate                              validate a package's .pc file
  --define-prefix                         try to override the value of prefix for each .pc file found with a guesstimated value based on the location of the .pc file
  --dont-define-prefix                    don't try to override the value of prefix for each .pc file found with a guesstimated value based on the location of the .pc file
  --prefix-variable=PREFIX                set the name of the variable that pkg-config automatically sets
```
## UseCase

Usecase | CMD
-- | --
查看链接信息 | `pkg-config [package-name] --libs`
查看预处理和编译 Flags | `pkg-config [package-name] --cflags`


```
$ pkg-config opencv4 --libs --cflags

-I/usr/include/opencv4/opencv -I/usr/include/opencv4 -lopencv_stitching -lopencv_aruco -lopencv_bgsegm 
-lopencv_bioinspired -lopencv_ccalib -lopencv_dnn_objdetect -lopencv_dnn_superres -lopencv_dpm -lopencv_highgui 
-lopencv_face -lopencv_freetype -lopencv_fuzzy -lopencv_hdf -lopencv_hfs -lopencv_img_hash -lopencv_line_descriptor 
-lopencv_quality -lopencv_reg -lopencv_rgbd -lopencv_saliency -lopencv_shape -lopencv_stereo -lopencv_structured_light 
-lopencv_phase_unwrapping -lopencv_superres -lopencv_optflow -lopencv_surface_matching -lopencv_tracking 
-lopencv_datasets -lopencv_text -lopencv_dnn -lopencv_plot -lopencv_ml -lopencv_videostab -lopencv_videoio -lopencv_viz 
-lopencv_ximgproc -lopencv_video -lopencv_xobjdetect -lopencv_objdetect -lopencv_calib3d -lopencv_imgcodecs 
-lopencv_features2d -lopencv_flann -lopencv_xphoto -lopencv_photo -lopencv_imgproc -lopencv_core
```

## `*.pc` 文件信息

- **/usr/lib/x86_64-linux-gnu/pkgconfig/opencv4.pc**
```
# Package Information for pkg-config

prefix=/usr
exec_prefix=${prefix}
libdir=${exec_prefix}/lib/x86_64-linux-gnu
includedir_old=${prefix}/include/opencv4/opencv
includedir_new=${prefix}/include/opencv4

Name: OpenCV
Description: Open Source Computer Vision Library
Version: 4.2.0
Libs: -L${exec_prefix}/lib/x86_64-linux-gnu -lopencv_stitching -lopencv_aruco -lopencv_bgsegm -lopencv_bioinspired -lopencv_ccalib -lopencv_dnn_objdetect -lopencv_dnn_superres -lopencv_dpm -lopencv_highgui -lopencv_face -lopencv_freetype -lopencv_fuzzy -lopencv_hdf -lopencv_hfs -lopencv_img_hash -lopencv_line_descriptor -lopencv_quality -lopencv_reg -lopencv_rgbd -lopencv_saliency -lopencv_shape -lopencv_stereo -lopencv_structured_light -lopencv_phase_unwrapping -lopencv_superres -lopencv_optflow -lopencv_surface_matching -lopencv_tracking -lopencv_datasets -lopencv_text -lopencv_dnn -lopencv_plot -lopencv_ml -lopencv_videostab -lopencv_videoio -lopencv_viz -lopencv_ximgproc -lopencv_video -lopencv_xobjdetect -lopencv_objdetect -lopencv_calib3d -lopencv_imgcodecs -lopencv_features2d -lopencv_flann -lopencv_xphoto -lopencv_photo -lopencv_imgproc -lopencv_core
Libs.private: -ldl -lm -lpthread -lrt
Cflags: -I${includedir_old} -I${includedir_new}
```

