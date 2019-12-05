# Gallery2
AS版本的Gallery2,基于AOSP7.1

### 我做了什么
##### (1) 完完全全的AS代码结构
##### (2) 代码合并，将原来三个目录的代码合并到一起，包名不变
##### (3) 编译好so，移到主工程libs
##### (4) 去除重复的string，原来标有no_sdcard的全部去除，只保留default的
##### (5) 处理了退出的crash异常，详见在DataManager的326行和LocalSource的272行
##### (6) 处理了裁剪在低分辨率crash的问题(拷贝了一份裁剪的dimens到values)

### 已知的问题
##### (1) 图片编辑不可用，因为raw文件夹下的bc32和bc64不会被打包的apk里面，ScriptC_convolve3x3初始化会找不到资源crash,我已经在build.gralde加了代码，但是似乎不生效，如有知道的同学请告知
```
res.srcDirs += [
                    'src/main/res/raw/bc32',
                    'src/main/res/raw/bc64',
            ]
```
##### (2) 设置不可用，设置页面是空实现，目前屏蔽掉了
##### (3) 其它问题待发现
