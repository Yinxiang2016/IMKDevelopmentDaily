#### 关于 自定义控件  
- 单个 View:  
通过 `Canvas` 和 `Paint` 进行绘制. 这个教程比较多, 传统的做法.  

https://developer.android.com/training/custom-views/index.html

- ViewGroup:  
后来发现首选是 `View.inflate()`. 前几天 写过 一个 自定义Layout, 继承自 `RelativeLayout`.  
控件 都是 `addView()` 加进去的, 属性控制 都是通过代码, 没法实时预览, 很是麻烦啊.  

http://trickyandroid.com/protip-inflating-layout-for-your-custom-view/  
http://www.vogella.com/tutorials/AndroidCustomViews/article.html  
http://javatechig.com/android/creating-custom-views-in-android-tutorial  
http://blog.csdn.net/lmj623565791/article/details/38352503  


#### 关于 不透明度  
此外, 注意 `alpha channel` 与 `opacity`/`opaque` 区别与联系.  
色码 `ffffff` 全白, `000000` 全黑.  
xml 中, `alpha = 00` 完全透明, `alpha = FF` 完全不透明.  
ps 中, `opacity = 0%` 完全透明, `opacity = 100%` 完全不透明.  

完全透明: `full transparent`  
半透明 (通常 `alpha = 0.5`): `translucence`  
完全不透明: `full opaque`  

##### 结论  
- `opaque 90%` 等效于 `alpha = 0.9` 等效于 `ARGB(230, r10, g10, b10)` 等效于 `0xE5r16g16b16` 等效于 `#E5r16g16b16`  
- `alpha 通道` 可以理解为 `不透明度`

值域 表示法:  
- 百分比: `[0%, 100%]`  
- 百分比 变形: `[0.0, 1.0]`  
- 10进制: `[0, 255]`  
- 16进制: `[00, FF]`  
