# 序
感谢 **iOS-火烈鸟(QQ 707791151)** 对本文的勘误.  
**本文 若干处 是 imknown 个人见解, 如有错误, 欢迎指正~**

# 术语
**<硬件规格>** 表示 `不能够` 轻易改变.  
**<硬件规格>** 通常 只影响 用户的 `直观视觉感受`.  
**并不会** 直接影响到 开发者 进行 `UI的适配`.

#### 基本单位术语
- pt(point): 磅 **<硬件规格>**
- px(pixel): 像素
- in(inch/″): 英寸 **<硬件规格>**
- dip/dp(device-independent pixel): 设备独立像素
- sp(scale-independent pixel): 比例独立像素
- density: 密度

#### 分辨率术语
- pr(physical resolution): (特指硬件层面的)物理分辨率 **<硬件规格>**
- prW(physical resolution width): 物理分辨率的 宽(特指单位 px) **<硬件规格>**
- prH(physical resolution height): 物理分辨率的 高(特指单位 px) **<硬件规格>**
- prWdp(physical resolution width in dp): 物理分辨率的 宽(单位 dp) **<硬件规格>**
- prHdp(physical resolution height in dp): 物理分辨率的 高(单位 dp) **<硬件规格>**

------

- sr(system resolution): (特指软件层面的)系统分辨率 (由 ROM和用户 共同决定, 可变)
- srW(system resolution width): 系统分辨率的 宽 (特指单位 px, 可变)
- srH(system resolution height): 系统分辨率的 高 (特指单位 px, 可变)
- srWdp(physical resolution width in dp): 物理分辨率的 宽 (单位 dp, 可变)
- srHdp(physical resolution height in dp): 物理分辨率的 高 (单位 dp, 可变)

#### 缩写
- PPI(pixels per inch): 每英寸像素数 **<硬件规格>**
- DPI(dots per inch): 每英寸点数 (由 ROM/用户 决定, 可变)
- BIR(base inch ratio): 基本英寸比例 **<硬件规格>**
- DPS(device physical size (unit in inch)): 设备物理尺寸(单位: 英寸) **<硬件规格>**
- TSS(text size scale): 文本字号比例 (由用户决定)

# 各平台 默认 1:1 DPI
| 平台             | 值   |
| ---------------- | :--: |
| MacOS / iOS      | 72   |
| Windows / Ubuntu | 96   |
| Android          | 160  |
参考: http://askubuntu.com/questions/197828/how-to-find-and-change-the-screen-dpi

# Android 常用 DPI 常量
| 缩写    | 值   | 值 / mdpi |
| ------: | :--: | :--:     |
| ldpi    | ~120 | ~¾       |
| mdpi    | ~160 | ~1       |
| tvdpi   | 213  | 1⅓       |
| hdpi    | ~240 | ~1½      |
| xhdpi   | ~320 | ~2       |
| 420dpi  | 420  | 2⅝       |
| xxhdpi  | ~480 | ~3       |
| 560dpi  | 560  | 3½       |
| xxxhdpi | ~640 | ~4       |

P.S.: `Google` 把 `mdpi` 也称作 `Baseline`.

# 分辨率
参考
- https://zh.wikipedia.org/wiki/%E6%98%BE%E7%A4%BA%E5%88%86%E8%BE%A8%E7%8E%87%E5%88%97%E8%A1%A8
- https://zh.wikipedia.org/wiki/%E5%AE%BD%E5%B1%8F%E6%89%A9%E5%B1%95%E5%9B%BE%E5%BD%A2%E9%98%B5%E5%88%97#/media/File:Vector_Video_Standards2.svg
- http://www.reinmedical.com/en/knowledge-technology/monitor-resolutions-overview.html
- http://superuser.com/questions/977654/what-is-the-difference-between-4k-uhd-and-qhd-do-we-agree-on-one-official-reso

#### 常用
| 缩写  | pr                                        | ratio |
| ----- | :---------------------------------------: | :---: |
| 240P  | 320x240(QVGA)                             | 4:3   |
| 320P  | 480x320(HVGA)                             | 3:2   |
| 480P  | 800x480(WVGA)                             | 5:3   |
| 720P  | 1280x720(HD, **手机主流**)                 | 16:9  |
| 720P  | 1280x768(WXGA)                            | 15:9  |
| 720P  | 1280x800(WXGA, **平板多用**)               | 16:10 |
| 1080P | 1920x1080(FHD)                            | 16:9  |
| 2K    | 2560x1440(QHD / Quad HD / WQHD, **主流**)  | 16:9 |

#### 不常用
| 缩写 | pr                     | ratio  |
| --- | :---------------------: | :---: |
| 2K  | 2048×1536(QXGA)         | 4:3   |
| 2K  | 2560×1600(WQXGA)        | 16:10 |
| 2K  | 2560x2048(QSXGA)        | 5:4   |
| 3K  | 3200x2048(QUXGA)        | ~17:9 |
| 3K  | 3840x2160(QFHD / UHD)   | 16:9  |
| 3K  | 3840x2400(QUXGA)        | 4:3   |
| 4K  | 4096x2160(4K Ultra HD)  | ~17:9 |
| 5K  | 5120x4096(HSXGA)        | 5:4   |
| 6K  | 6400×4096(WHSXGA)       | 25:16 |
| 6K  | 6400x4800(HUXGA)        | 4:3   |
| 7K  | 7680x4800(WHUXGA)       | 16:10 |

# DPI 与 sr 关系 (注意不是 pr)
#### 常规手机 (通常 DPS < 6.0″)
| DPI     | sr    |
| ------: | :---: |
| mdpi    | 320P  |
| hdpi    | 480P  |
| xhdpi   | 720P  |
| xxhdpi  | 1080P |
| xxxhdpi | 2K    |

#### 常规平板 (通常 DPS ≥ 6.0″)
| DPI    | sr    |
| -----: | :---: |
| ldpi   | 480P  |
| mdpi   | 720P  |
| tvdpi  | 720P  |
| hdpi   | 1080P |

#### 常规电视 (通常 DPS 很大, 比如说 55″)
| DPI    | sr      |
| -----: | :-----: |
| tvdpi  | 720P    |
| xhdpi  | 1080P   |

#### 常规可穿戴设备 (通常 DPS 很小, 比如说 2″)
| DPI    | sr       |
| -----: | :------: |
| tvdpi  | 280x280  |
| hdpi   | 360x360  |

# 运算定义
```
- BIR = 1/72
- 令 S = prW^2 + prH^2
- PPI = diagonal px / DPS = (√‾S) / DPS
- DPI ≊ PPI (约等于 或者 等于)
- density = DPI / mdpi
- pr = prW * prH = prWdp * prHdp
- sr == pr 的时候(其他任何参数均相同), 显示效果最佳, 否则模糊
```

# 单位换算
```
- 1 pt = BIR in
- 1 px = 1 pt * DPI * BIR
- 1 dp = 1 px * density
- 1 sp = 1 dp * TSS
```

# 小例子: 手机 显示 100dp
设 `C = 100dp`  

| pr        | S       | √‾S        |
| --------- | ------- | ---------- |
| 1440x2560 | 8627200 | 2937.20956 |
| 1080x1920 | 4852800 | 2202.90717 |
| 800x1280  | 2278400 | 1509.43698 |
| 768x1280  | 2228224 | 1492.72369 |
| 720x1280  | 2156800 | 1468.60478 |
| 480x800   | 870400  | 932.95230  |

| 型号          | DPS   | PPI    | DPI    | density | sr        | srWdp  | srWdp / C | srHdp  | srHdp / C |
| ------------- | ----  | ------ | ------ | ------- | --------- | ------ | --------- | ------ | --------- |
| Pixel XL      | 5.5″  | 534.04 | 560dpi | 3.5     | 1440x2560 | 411.43 | 4.1143    | 731.43 | 7.3143    |
| Pixel         | 5.0″  | 440.58 | xxhdpi | 3       | 1080x1920 | 360    | 3.6       | 640    | 6.4       |
| Nexus 6P      | 5.7″  | 515.30 | 560dpi | 3.5     | 1440x2560 | 411.43 | 4.1143    | 731.43 | 7.3143    |
| Nexus 5X      | 5.2″  | 423.64 | 420dpi | 2.625   | 1080x1920 | 411.43 | 4.1143    | 731.43 | 7.3143    |
| Nexus 6       | 5.96″ | 492.82 | 560dpi | 3.5     | 1440x2560 | 411.43 | 4.1143    | 731.43 | 7.3143    |
| Nexus 5       | 4.95″ | 445.03 | xxhdpi | 3       | 1080x1920 | 360    | 3.6       | 640    | 6.4       |
| Nexus 4       | 4.7″  | 317.60 | xhdpi  | 2       | 768x1280  | 384    | 3.84      | 640    | 6.4       |
| Galaxy Nexus  | 4.65″ | 315.83 | xhdpi  | 2       | 720x1280  | 360    | 3.6       | 640    | 6.4       |
| Nexus S       | 4.0″  | 223.24 | hdpi   | 2       | 480x800   | 240    | 2.4       | 400    | 4         |
| Nexus One     | 3.7″  | 252.15 | hdpi   | 2       | 480x800   | 240    | 2.4       | 400    | 4         |

# 小例子: 平板 显示 100dp
设 `C = 100dp`  

| pr        | S       | √‾S        |
| --------- | ------- | ---------- |
| 1800x2560 | 9793600 | 3129.47280 |
| 1600x2560 | 9113600 | 3018.87396 |
| 1536x2048 | 6553600 | 2560       |
| 1200x1920 | 5126400 | 2264.15547 |
| 800x1280  | 2278400 | 1509.43698 |

| 型号          | DPS    | PPI    | DPI    | density | sr        | srWdp  | srWdp / C | srHdp  | srHdp / C |
| ------------- | -----  | ------ | ------ | ------- | --------- | ------ | --------- | ------ | --------- |
| Pixel C       | 9.94″  | 314.84 | xhdpi  | 2       | 1800x2560 | 900    | 9         | 1280   | 12.8      |
| Pixel 10      | 10.05″ | 300.39 | xhdpi  | 2       | 1600x2560 | 800    | 8         | 1280   | 12.8      |
| Pixel 9       | 8.86″  | 288.94 | xhdpi  | 2       | 1536x2048 | 768    | 7.68      | 1024   | 10.24     |
| Pixel 7(2012) | 7.0″   | 323.45 | xhdpi  | 2       | 1200x1920 | 600    | 6         | 960    | 9.6       |
| Pixel 7       | 7.02″  | 215.02 | tvhdpi | 1.333   | 800x1280  | 600    | 6         | 640    | 6.4       |

# 常用命令
### 获取 显示的一些参数
``` bash
adb shell dumpsys display | grep mBaseDisplayInfo
```

### 修改 sr
设置到 1024x768:
``` bash
am display-size 1024x768
```

恢复:
```
am display-size reset
```

参考:
- http://stackoverflow.com/a/28618961/2782426

### 修改 DPI
``` bash
adb shell wm density 420
adb reboot
```

或者 修改 `build.prop` 然后 至少重启 `SystemUI`:
``` properties
ro.sf.lcd_density=420
```

### Android 7.x 启用 Freeform
启用:
``` bash
adb shell settings put global enable_freeform_support 1
adb reboot
```

禁用:
``` bash
adb shell settings put global enable_freeform_support 0
adb reboot
```

参考:
- http://www.codeceo.com/article/android-multi-window.html

# 跋
### 原型工具
- Mobile app prototyping with Justinmind wireframing tool  
https://www.justinmind.com/mobile-prototyping

- Justinmind6.X软件及汉化包下载地址 – Justinmind•学习站  
http://www.jmstu.com/588.html

- PxCook - 标注切图，一起搞定  
http://www.fancynode.com.cn/pxcook
