### 1.介绍一下标准的css盒子模型? 与低版本的IE的盒子模型有什么不同
### 标准盒模型 : 宽度 = 内容的宽度(content) + border + padding + margin
### 低版本IE盒模型 : 宽度 = 内容宽度(content + border + padding) + margin


### 2.box-sizing属性?
### 该属性用来控制盒子模型的解析模式,一般默认的值是content-box
### content-box : w3c的标准盒模型,你设置元素的height/width,设置的就是元素的宽高也就是content部分的宽和高
### border-box  : IE传统盒模型(怪异盒模型),设置元素的height/width属性指的是border + padding + content部分的宽高


### 3.CSS选择器有哪些?哪些属性可以继承
### css选择器 : id选择器(#idname) | 类选择器(.classname) | 标签选择器(div,h1,p) | 相邻元素选择器(h1 + p) | 子选择器(ul > li) | 后代选择器(li a) | 通配符选择器(*) | 属性选择器(a[rel='external']) | 伪类选择器(a:hover,li : nth-child)
### 可以继承的属性 : font-size, font-family, color
### 不可继承的样式 : border,paddig,margin,width,height
### 优先级 : !important > [id > class > tag]
### !important(代表权重) 比内联优先级高

### 4.CSS优先级算法如何计算
### 元素运算符 : 1
### class选择器 : 10
### id选择器 : 100
### 元素标签 : 1000
###     1.!important 声明的样式优先级最高,如果冲突再进行运算
###     2.如果两个优先级相同,那么选择最后出现的样式
###     3.继承得到的样式优先级最低


### 5.CSS新增的伪类有哪些
### p:first-of-type 选择属于其父元素的首个元素
### p:last-of-type  选择属于其父元素的最后元素
### p:only-of-type  选择属于其父元素唯一的元素
### p:only-child 选择属于父元素的唯一子元素
### p:nth-child(2)  选择属于其父元素的第二个子元素
### :enabled :disabled 表单控件的禁用状态
### :checked 单选框或复选框被选中


### 6.如何居中div? 如何居中一个浮动元素? 如何让绝对定位的div居中
### (1) 给div设置宽高 , 设置div的margin值,左右为auto
### (2) 当div是浮动的时候,让div左和上都是50%,然后设置margin-left为负的二分之一宽,让margin-top是负的二分之一高
### (3) 当div只是绝对定位,不浮动的时候,我们让div的左右值相等,然后调整margin左右都为auto就可以实现
### (4) flex 水平垂直居中 我们要在需要操作的元素外层再套一个父元素,在父元素上设置display:flex属性,display:flex + justify-content:center子元素自动水平居中,如果想让垂直居中需要添加align-items:center或者align-content:center


### 7.display有哪些值? 以及他们的作用是什么
### inline(默认) -- 内联
### none -- 隐藏
### block -- 块显示
### table -- 表格显示   (相当于table标签,现在基本上不用了,因为不利于seo,不符合语义化)
### list-item -- 项目列表
### inline-block -- 行内块显示


### 8.position的值
### static(默认) : 按照正常文档流进行排列
### relative(相对定位) : 不脱离文档流,参考自身静态位置通过top,bottom,left,right定位;
### absolute(绝对定位) : 参考距离最近的一个不为static的父集进行定位,通过top,bottom,left,right定位
### fixed(固定定位) : 所固定的参照对象是可视的窗口


### 9.CSS3有哪些新特性
### (1).rgba透明度
### (2).background-image background-origin(content-box/padding-box/border-box) | background-size | background-repeat
### (3).word-wrap(对长的不可分割的单词换行) 
### (4).文字阴影 : text-shadow : 5px 5px 5px #FF000 (水平阴影,垂直阴影,模糊距离,阴影颜色)
### (5).font-face属性 : 定义自己的字体
### (6).圆角(边框半径) : border-radius属性用于创建圆角
### (7).边框图片 : border-image : url(border.png) 30 30 round
### (8).盒阴影 : box-shadow : 10px 10px 5px #red
### (9).媒体查询 : 定义两套css,当浏览器尺寸发生变化的时候采用不同的属性


### 10.请解释一下CSS3的flexbox(弹性盒布局模型),以及适用场景?
### 该布局模型的目的是提供一种更加高效的方式来对容器中的条目进行布局,对齐和分配空间.
### 在传统的布局方式当中,block布局是把块在垂直方向上从上到下依次排列的;而inline布局则是在水平方向来排列.弹性盒布局并没有这样内在的方向限制,可由设置人员自由操作
### 适用场景 : 弹性布局适合于移动前端开发,在Android和ios上也完美支持


### 11.用纯css创建一个三角形的原理是什么
### 首选设置元素的宽高为0,设置它的边框样式
     ```js
            width: 0; 
            height: 0;
            border-top: 20px solid yellow;
            border-right: 20px solid green;
            border-left: 20px solid blue;
            border-bottom: 20px solid red;
     ```
###


### 12.一个满屏品字布局如何设计 
### 第一种 : 1.三块的宽高是确定的 2.上面的第一块用margin : 0 auto; 居中
###          3.下面两块用float或者inline-block不换行
###          4.用margin调整位置使他们居中
### 第二种 : 1.把上面的div设置成100%,下面的两个分别宽50%,然后使用float或者inline使其换行


### 13.常见的兼容性问题?
### (1).不同浏览器的标签默认的margin和padding不一样,所以我们在设计css样式之前要用*{}来初始化
### (2).IE6双边距bug: 块属性标签float后,又有横行的margin情况下,在ie6当中显示margin比设置的大,解决方法 : display:inline; 将其转化为行内属性
### (3).渐进识别的方法,从总体中逐渐排除局部.首先巧妙的使用"9"这一标记,将ie浏览器从所以情况中分离出来.接着,再次使用"+" 将ie8和ie7 | ie6分离开,这样ie8已经独立识别了
```js
  background-color:#f1ee18;/*所有识别*/
  .background-color:#00deff\9; /*ie6 / 7 / 8识别*/
  +backgroun-color:#a200ff; /*IE6 / IE7识别*/
  _background-color:#1e0db1; /*IE6识别*/

```
### (4).设置较小的高度标签(一般小于10px),在ie6,ie7中高度超出自己设置高度.解决方法 : 给超出高度的标签设置 : overflow:hidden ; 或者设置行高line-height小于你设置的高度
### (5).ie下,可以使用获取常规属性的方法来获取自定义属性,也可以使用getAttribute()获取自定义属性;firefox下,只能使用getAttribute()获取自定义属性,解决方法都使用getAttribute()获取自定义属性
### (6).Chrome中午界面会默认将小于12px的文本强制按照12px显示,可以通过加入css属性-webkit-text-size-adjust:none; 解决
### (7).超链接访问之后hover样式就不出现了,被点击访问过超链接样式不再具有hover和active,解决方法是改变CSS属性的排列顺序:L-V-H-A(love hate): a:link{},a:visited{},a:hover{},a:active{}


### 14.为什么要初始化CSS样式
### 因为浏览器的兼容性有问题,不同浏览器对某些标签的默认值是不一样的,如果没有初始化css往往会出现浏览器之间的页面显示差异


### 15.absolute的containing block计算方式跟正常流有什么不同? 
### 无论什么情况都要先找到其父元素中最近的position值不为static的元素再判断,
### (1).若此元素为inline元素,则containing block为能够包含这个元素生成的第一个和最后一个inline box的padding box(除margin,border外的区域)的最小矩阵
### (2).否则,则由这个祖先元素的padding box构成
### 如果都找不到,则为initial containing block
### 补充 : (1).static(默认的)/relative:简单的说就是他的父元素的内容框(即去掉padding的部分)
###        (2).absolute:向上找最近的定位为absolute/relative的元素
###        (3).fixed:它的containing block一律为根元素(html/body)


### 16.CSS里的visibility属性有个collapse属性值?在不同的浏览器中以后有什么区别
### 当一个元素的viisbility属性被设置成collapse值后,对于一般的元素,它的表现跟hidden是一样的
### (1).chrome当中,使用collapse值和使用hidden没有区别
### (2).firefox,opera和ie,使用collapse值和使用display:none没有什么区别


### 17.display:none 与 visibility: hidden的区别
### display:none 不显示对应的元素,在布局当中不再分配空间了(回流+重绘)
### visibility:hidden 隐藏了对应元素,在文档布局中仍保留原来的空间(重绘)


### 18.position跟display / overflow / float这些特性相互叠加后会怎么样? 
### display属性规定元素生成的框的类型,position属性规定元素的定位类型,float是一种布局方式,定义元素的浮动方向
### 类似于优先级机制 : position:absolute / fixed优先级最高,有他们在时,float不起作用,display值需要调整,float或者absolute定位的元素,只能是块元素或表格


### 19.对应BFC规范(块级格式化上下文:block formatting context)的理解
### BFC规定了内部的Block Box如何布局
### 定位方案:
###         (1).内部的box会在垂直方向上一个接着一个的放置
###         (2).Box垂直方向的距离由margin决定,属于同一个BFC的两个相邻Box的margin会发生重叠
###         (3).每个元素的margin box的左边,与包含块border box的左边相接触
###         (4).BFC的区域不会与float box 重叠
###         (5).BFC页面上的一个隔离的独立容器,容器里面的子元素不会影响到外面的元素
###         (6).计算BFC高度的时候,浮动元素也会参与计算
###  满足以下条件就会触发bfc
###         (1).根元素,即html
###         (2).float的值不为none(默认)
###         (3).overflow的值不为visible(默认)
###         (4).display的值为inline-block . table-cell . table-caption
###         (5).position的值为absolute或fixed


### 20.为什么会出现浮动和什么时候需要清除浮动? 清除浮动的方法
### 浮动元素碰到包含它的边框或者浮动元素的边框停留,由于浮动元素不在文档流当中,所以文档流的块框就像不存在一样,浮动元素就会浮到文档流的块框上
### 浮动带来的问题:
###              (1).父元素的高度无法被撑开,会影响父元素同级的元素      
###              (2).与浮动元素的同级非浮动元素(内联元素)会跟随其后
###              (3).若非第一个元素浮动,则该元素之前的元素也需要浮动,否则会影响页面显示的结构
### 清除浮动的方法:
###               (1).父集div定义height
###               (2).最后一个浮动元素加空div标签，并添加样式clear:both
###               (3).包含浮动元素的父标签添加样式overflow为hidden或auto
###               (4).父级div定义zoom\
###               ///我的方法
###               最简单的就是在父集上也添加上浮动,这样父集的div边框也就被浮动了变成了inline-block，也就能看见之前被浮动的div内容
###           最正规的就是添加一个伪类，在使用这个伪类的时候，记得写上content：“”； 这个content里面的引号就算里面没有内容也要写上
###           ::after{
###           content:"";
###           display:block;     (切记只有block可以)
###            claer:both;
###           }
###           以上就是使用伪类清除元素的标准格式。
###           还有就是在父集上添加一个display，让他变成inline-block格式


### 21.上下margin重合的问题
### 在重合元素外层裹一层容器,并触发该元素的bfc


### 22.设置元素浮动后,该元素的display值为多少
### 自动变成display


### 23.移动端的布局用过媒体查询吗?
### 通过媒体查询可以为不同大小和尺寸的媒体定义不同的css,适应相应的设备的显示
### (1).<head>里面 
### <link rel="stylesheet" type="text/css" href="xxx.css" media="only screen and (max-device-width:480px)">
### (2).CSS : @media only screen and (max-device-width:480px) {/css样式/}


### 24.使用css预处理器
### Less  sass


### 25.优化css,提高性能的方法有哪些?
### (1).避免过度约束
### (2).避免后代选择符
### (3).避免链式选择符
### (4).使用紧凑的语法
### (5).避免不必要的命名空间
### (6).避免不必要的重复
### (7).最好使用表示语义的名字,一个好的类名应该是描述他是什么而不是像什么
### (8).避免! important ,可以选择其它选择器
### (9).尽可能的精简规则,你可以合并不同类里面的重复规则


### 26.浏览器是如何解析css选择器的
### CSS选择器的解析是从右向左解析的.如果从左往右匹配,发现不符合规则的,需要进行回溯,会损失大量性能.若从右向左匹配,先找到所有的最右节点,对于每个节点,向上寻找其父节点直到找到根元素,或满足条件的匹配,则结束该分支的遍历.两种匹配规则的性能差别很大,是因为从右向左的匹配在第一步就筛选掉了大量不符合条件的最右节点(叶子节点),从左向右的匹配规则的性能都浪费在了失败的查找上面.
### 而在css解析完成后,需要将解析的结构与dom Tree的内容一起进行分析建立一颗Render Tree,最终来进行绘图.在建立Render Tree时候,(webkit中的[Arrachment]过程),浏览器就要为每个DOM Tree中的元素根据CSS的解析结果(Style Rules)来确定生成怎样的Render Tree


### 27.在网页当中应该使用奇数还是偶数的字体? 为什么?
### 应该使用偶数字体,偶数字体相对更容易和web设计的其它部分构成比例关系, windows 自带的点阵宋体(中易宋体) 从 Vista开始只提供12 , 14 , 16px这三个大小的点阵,而 13 , 15 , 17px时用的是小一号的点(即使每个字占的空间大了 , 但是点阵没变) 于是略显稀疏


### 28.margin和padding分别适合什么场景使用?
### 何时使用margin : 
###                 (1).需要在border外侧添加空白
###                 (2).空白处不需要背景色
###                 (3).上下相连的两个盒子之间的空白,需要相互抵消时候
### 何时使用padding : 
###                 (1).需要在border内侧添加空白
###                 (2).空白处需要背景颜色
###                 (3).上下相连的两个盒子的空白,希望为两者之和
### 兼容性问题 : 在IE5 , IE6中 , 为float的盒子指定margin时,左侧的margin可能会变成两倍的宽度,通过改变padding或指定盒子的display : inline解决


### 29.元素竖向的百分比设定是相对于容器的高度吗?
### 当按照百分比设定一个元素的宽度时,它是相对于父容器的宽度计算的,但是,对于一些表示竖向距离的属性,例如padding-top,padding-bottom,margin-top,margin-bottom等,当安装百分比来设定他们的时候,依据的也是父容器的宽度,而不是高度


### 30.全屏滚动的原理是什么? 用到了css的哪些属性?
### (1).原理有点类似于轮播,整体元素一直排列下去,假设有5个需要展示的全屏页面,那么高度是500% , 只是展示100% , 剩下的可以通过transform进行y轴定位,也可以通过margin-top实现
### (2).用到了 overflow:hidden; transition : all 1000ms ease;


### 31.什么是响应式设计? 响应式设计的基本原理是什么? 如何兼容低版本的IE?
### 响应式网站设计(Responsive Web design)是一个网站能够兼容多个终端,而不是为每一个终端都做一个特定的版本
### 基本原理是通过媒体查询监测不同的设备屏幕尺寸做处理.
### 页面头部必须有meta声明的viewport
### <meta name = "viewport" content = "width=device-width, initial-scale = 1.0 maximum-scale = 1,user-scalable=no">


### 32.视差滚动效果?
### 视差滚动(Parallax Scrolling) 通过在网页向下滚动的时候,控制背景的移动速度比前景的移动速度慢来创建令人惊叹的3D效果
### 1.css3实现
###   优点 : 开发时间段,性能和开发效率比较好,缺点是不能兼容低版本的浏览器
### 2.jQuery实现
###   通过控制不同层滚动的速度,计算每一层的时间,控制滚动效果
###   优点 : 能兼容到各个版本,效果可控性好
###   缺点 : 对开发者要求高
### 3.插件实现方式
###   例如 : parallax-scrolling , 兼容性十分好


### 33.::before 和 : after 中双冒号和单冒号有什么区别 ? 解释一下这两个伪元素的作用
### (1).单冒号(:)用于css3伪类,双冒号(::)用于css3伪元素
### (2).::before就是以一个子元素的存在,定义在元素主体内容之前的一个伪元素.并不存在dom之中,只存在页面之中
### :before 和 :after这两个伪元素,是在css2.1里面新出现的.起初,伪元素的前缀使用的是单冒号语法,但是随着web的进化,在css3的规范里面,伪元素的语法被改成使用双冒号,成为::before , ::after


### 34.你对line-height是如何理解的?
### 行高指的应该是一行文本的高度,具体来说是两行文件间基线的距离.css中起高度作用的是height和line-height,没有定义height属性,最终起表示作用一定是line-height
### 单行文本居中 : 把line-height值设置为height一样大小的值就可以实现,其实把height删掉也可以
### 多行文本居中 : 需要设置display属性为inline-block


### 35.如何让Chrome支持小于12px1的文字?
### p{font-size:10px; -webkit-transform:scale(0.8);} // 0.8是缩放比例//


### 36.让页面的字体变清晰,变细用css怎么做?
### -webkit-font-smoothing在window系统下没有起作用,但是在ios设备上起作用-webkit-font-smoothing : antialiased是最佳的,灰度平滑


### 37.position:fixed;在android下无效怎么处理?
### <meta name="viewport" content="width=device-width , initial-scale=1.0 , maximum-scale=1.0 , minimum-scale=1.0 , user1-scalable=no"/>


### 38. 如果需要手动写动画,你认为最小时间间隔是多少,为什么?
### 大多数显示器默认频率是60HZ , 即1秒刷新60次 , 所以理论上最小间隔应该为 1/60 * 1000ms = 16.7ms


### 39.li与li之间有看不见的空白间隔是什么原因引起的? 有什么解决方法?
### 行框的排列会受到中间空白 (回车空格) 等的影响 , 因为空格也属于字符 , 这些空白也会被应用样式 , 占据空间 , 所以会有间隔 , 把字符大小设为0 , 就没有空格了
### 解决方法 : 
###        (1).可以将<li>代码全写在一排
###        (2).浮动li中float : left
###        (3).在ul中用font-size : 0(谷歌不支持); 可以使用letter-space : -3px


### 40.display : inline-block 什么时候会显示间隙
### (1).有空格时候会有间隙  解决:移除空格
### (2).margin正值的时候    解决:使margin负值
### (3).使用font-size时候   解决:font-size:0 , letter-spacing , word-spacing


### 41.有一个高度自适应的div,里面有两个div,一个高度100px,希望另一个填满剩下的高度
### 外层div使用position : relative; 高度要求自适应的div使用position : absolute; top:100px; bottom:0; left:0


### 42.png , jpg , gif这些图片格式解释一下, 分别什么时候用. 有没有了解过webp
### (1). png是便携式网路图片(Portable Network Graphics) 是一种无损数据压缩位图文件格式. 优点使:压缩比高,色彩好,大多数地方都可以用
### (2).jpg是一种针对相片使用的一种失真压缩方法,是一种破坏性的压缩,在色调及颜色平滑变化做的不错. 在www上,被用来储存和传输照片的格式
### (3).gif是一种位图文件格式,以8位色重现真色彩的图像. 可以实现动画效果
### (4).webp格式是谷歌在2010年推出的图片格式,压缩率只有jpg的2/3,大小比png小了45%,缺点是压缩的时间更久了,兼容性不好,目前谷歌和opera支持


### 43.style标签写在body后与body前有什么区别?
### 页面加载自上而下,当然是先加载样式
### 写在body标签后由于浏览器以逐行方式对HTML文档进行解析,当解析到写在尾部的样式表(外联或写在style标签)会导致浏览器停止之前的渲染,等待加载且解析样式表完成之后重新渲染,在windows的IE下可能会出现fouc现象(即样式失效导致的页面闪烁问题)


### 44.CSS属性overflow属性定义溢出元素内容区会如何处理?
### 参数是scroll时候,必会出现滚动条
### 参数是auto时候,子元素内容大于父元素时出现滚动条
### 参数是visiable时候,溢出的内容出现在父元素之外
### 参数是hidden时候,溢出隐藏


### 45.阐述一下CSS Sprites
### 将一个页面涉及到的所有图片都包含到一张大图中去,然后利于CSS的background-image,background-repeat, background-position 的组合进行背景定位, 利用CSS Sprites能很好地减少网页http请求, 从而大大的提高页面的性能; CSS Sprites 能减少图片的字节


### 自增 : 伪类和伪元素
### 伪类 官方定义 : 其核心就是用来选择那些不能够被普通选择器选取的文档之外的元素 , 比如:hover
### 伪元素 官方定义 : 其核心就是需要创建通常不存在于文档中的元素,比如::before
### 定义不同 : 伪类即假的类,通常可以添加类来达到效果,伪元素即假元素,需要通过添加元素才能达到效果
###
###
###

