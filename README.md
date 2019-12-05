# Gallery2
一个可用Android Stusio编译的Gallery2，基于AOSP7.1(A Gallery2 that can be compiled with Android Stusio, based on AOSP7.1)

### 我做了什么
##### (1) 完完全全的AS代码结构
##### (2) 代码合并，将原来三个目录的代码合并到一起，包名不变
##### (3) 编译好so，移到主工程libs
##### (4) 去除重复的string，原来标有no_sdcard的全部去除，只保留default的
##### (5) 处理了退出的crash异常，详见在DataManager的326行和LocalSource的272行
##### (6) 处理了裁剪在低分辨率crash的问题(拷贝了一份裁剪的dimens到values)
- - -
### 已知的问题
##### (1) 图片编辑不可用，因为raw文件夹下的bc32和bc64不会被打包的apk里面，ScriptC_convolve3x3初始化会找不到资源crash,我已经在build.gralde加了代码，但是似乎不生效，如有知道的同学请告知
```
res.srcDirs += [
                    'src/main/res/raw/bc32',
                    'src/main/res/raw/bc64',
            ]
```
##### (2) 设置不可用，设置页面是空实现，目前屏蔽掉了
##### (3) 未适配权限申请，我把sdk版本改到了22
##### (4) 其它问题待发现...





---
---


### what did I do
##### (1) Complete AS code structure
##### (2) Code merge, merge the code of the original three directories together, package name unchanged
##### (3) Compile so, move to the main project libs
##### (4) Remove duplicate strings. All original tags marked with no_sdcard are removed. Only the default ones are retained.
##### (5) Handled the crash exception, see line 326 of DataManager and line 272 of LocalSource
##### (6) Fixed the issue of cropping at low resolution crash (copied a copy of cropped dimensions to values)
---
### Known issues
##### (1) Picture editing is not available, because bc32 and bc64 in the raw folder will not be packaged in the APK. ScriptC_convolve3x3 initialization will not find the resource crash. I have added code in build.gralde, but Does not seem to take effect, please let me know if you know
```
res.srcDirs += [
                    'src/main/res/raw/bc32',
                    'src/main/res/raw/bc64',
            ]
```
##### (2) Settings are unavailable. The settings page is empty. Currently blocked.
##### (3) I did not apply for permission, I changed the SDK version to 22.
##### (4) Other issues to be found ...
