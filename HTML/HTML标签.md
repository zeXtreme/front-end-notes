#语法
* 都是放在`<>`里面
* 闭合
* 一个或多个属性值
* 嵌套
* 注释`<!-- 注释内容 -->`

#全局属性
* id
 * 同一页面只能出现一次
* class
 * 同一页面可以出现多次
* style
 * 直接给标签加入css样式（不建议）
* title
 * 浮动信息（鼠标悬浮时出现）

#HTML标签


##文档章节
* body
* header
* nav
* aside
* article
* section
* footer
* hx



##标题
* 标题（h1~h6）



##文本
* 超链接
 * a
    - 创建指向另一个文档的链接
target属性可以为_self（当前窗口打开，默认），_blank（新窗口打开），或者一个iframe的name
    - 创建一个文档内部的锚点  
`<a href="#pay">点击支付</a><!-- 点击后跳转到id为pay的标签 --><div id="pay"></div>`
    - 链接到Email地址  
`<a href="mailto:zwy@zwy.me">联系我</a><!-- 点击之后打开系统默认的邮件客户端 -->`
* 强调
 * em，strong
    - em为语意上的强调（样式默认*斜体*）
    - strong为重要性的强调（样式默认**粗体**）
* 行内容器
 * span
无任何语意，用于同一行文字中不同样式
* 换行
 * br
* 引用
 * cite，q
    - cite
作品名
    - q
某人说的话
* 代码
 * code
* 格式化
 * b，i
    - b
关键词
    - i
技术术语

##组合内容
* div
 - 分区

 - 其他标签的容器
* 段落
 * p
* 列表
 - 无序列表
```html
<ul>
    <li>列表项</li>
    <li>列表项</li>
    <li>列表项</li>
</ul>
```
 - 有序列表
```html
<ol>
    <li>一</li>
    <li>二</li>
    <li>三</li>
</ol>
```
 - 自定义列表
```html
<dl>
    <dt>作者</dt>
    <dd>Cbuck Musciano</dd><!-- 一个dt可以有多个dd -->
    <dd>Bll Kennedy</dd>
    <dt>出版年</dt>
    <dd>2007-4</dd>
</dl>
```
* pre
 * 保留格式
* blockquote
 * 大段引用

##嵌入资源
* img嵌入图片  
`<img src="../cover.jpg" alt="封面"/><!-- alt属性会在图片加载失败时在占位框中显示 -->`
* iframe嵌入页面  
`<iframe src="http://www.163.com"></iframe>`
* object，embed嵌入外部资源
 * object
 * 
 ```html
<object type="application/x-shockwave-flash">
    <param name="movie" value="http://pdfReader.swf"/>
    <param mame="flashvars" value="http://book.pdf"/>
</object>
```
 * embed
 * 
 ```html
<embed type="application/x-shockwave-flash" src="http://pdfReader.swf" width="640" height="480"/>
```
* video嵌入视频(html5)
```html
<video autoplay loop controls="controls" poster="/img/poster.jpg"><!-- controls控制条的显示，poster视频的封面，加入autoplay可以使视频自动播放，加入loop属性使视频循环播放 -->
    <source src="movie.mp4" type="video/mp4"/>
    <source src="movie.webm" type="video/webm"/><!-- 不同浏览器支持的格式不同，在服务器上设置多种格式以兼容大部分浏览器 -->
    <source src="movie.ogg" type="video/ogg"/>
    <track kind="subtitles" src="video.srt" label="English"/>
    您的浏览器不支持video标签。<!-- 不支持video标签的浏览器显示这行文字 -->
</video>
```
* audio嵌入音频(html5)
```html
<audio autoplay loop controls="controls" poster="/img/poster.jpg"><!-- controls控制条的显示 -->
    <source src="audio.wav" type="audio/wav"/>
    <source src="audio.mp3" type="audio/mp3"/><!-- 不同浏览器支持的格式不同，在服务器上设置多种格式以兼容大部分浏览器 -->
    <track kind="subtitles" src="video.srt" label="English"/>
    您的浏览器不支持audio标签。<!-- 不支持audio标签的浏览器显示这行文字 -->
</audio>
```
* 嵌入图
 - canvas
基于像素
 - svg
矢量图
* 热点区域
 - map
 - area
```html
<img src="./res/map.png" alt="运动" width="509" height="644" usemap="#Map2"><!-- usemap定义了使用map -->
<map name="Map2">
  <area shape="rect" coords="0,0,313,245" href="http://www.xiupin.com/mainbrand/story?id=7012" target="_blank"><!-- shape定义形状，coords定义关键点 -->
  <area shape="rect" coords="313,0,500,285" href="http://www.xiupin.com/mainbrand/story?id=7013" target="_blank">
  <area shape="poligon" coords="0,244,270,240,346,374,0,425" href="http://www.xiupin.com/mainbrand/story?id=8003" target="_blank">
  <area shape="poligon" coords="0,432,270,427,310,540,313,635,0,635" href="http://www.xiupin.com/mainbrand/story?id=7015" target="_blank">
  <area shape="poligon" coords="287,386,509,388,508,633,331,632" href="http://www.xiupin.com/mainbrand/story?id=7014" target="_blank">
</map>
```

##表格
```html
<table>
    <caption>照片冲印价格详情</caption><!-- 表格标题 -->
    <thead><!-- 表头 -->
      <tr><th>相片尺寸</th><th>富士</th><th>柯达</th></tr><!-- 每一行是tr，th是加粗单元格，td是普通单元格 -->
    </thead>
    <tbody><!-- 表体 -->
      <tr><th>6寸</th><td>0.45</td><td>0.6</td></tr>
      <tr><th>全景6寸</th><td>0.45</td><td>0.6</td></tr>
      <tr><th>7寸</th><td>0.89</td><td>1</td></tr>
      <tr><th>8寸</th><td>1.69</td><td>2</td></tr>
      <tr><th>10寸</th><td>3.89</td><td>5</td></tr>
    </tbody>
    <tfoot><!-- 表尾 -->
      <tr><td colspan="3">运费8元/单，满99元免运费</td></tr><!-- colspan用于跨列，rowspan用于跨行 -->
    </tfoot>
  </table>
```

##表单
```html
<form action="/login"  method="post"><!-- action为表单提交地址 -->
    <fieldset><!-- 表单分区 -->
      <legend>照片选择</legend><!-- 表单分区的标题 -->
      <label for="file">选择照片</label><input type="file" id="file"><!-- label的for属性要与要表示的表单元素的id属性一致，input标签type属性为file时为文件选择按钮 -->
    </fieldset>
    <fieldset>
      <legend>综合设置</legend>
      <div>选择尺寸：</div>
      <div>
        <input type="checkbox" name="size" id="cb_0" value="5"><label for="cb_0" checked>5寸</label><!-- 复选框 -->
        <input type="checkbox" name="size" id="cb_1" value="6"><label for="cb_1">6寸</label>
      </div>
      <div>选择相纸：</div>
      <div>
        <input type="radio" name="material" id="rd_0" value="fushi"><label for="rd_0" >富士</label><!-- 单选框 -->
        <input type="radio" name="material" id="rd_1" value="keda"><label for="rd_1" >柯达</label>
      </div>
      <div>
        <label for="delivery">配送方式：</label>
        <select id="delivery"><!-- 下拉选择框 -->
            <option value="0">快递</option>
            <option value="1">EMS</option>
            <option value="2" selected>平邮</option><!-- selected使这一项默认选中 -->
        </select>
      </div>
      <div>
        <label for="description">商品描述：</label>
        <input type="text" id="description" placeholder="描述"><!-- 单行文本框，placeholder在用户无输入时显示 -->
      </div>
      <div>
        <label for="feedback">意见反馈：</label>
        <textarea name="feedback" rows="4" id="feedback"></textarea><!-- 多行文本框 -->
      </div>
    </fieldset>
    <div>
      <button type="submit">提交</button><!-- 提交表单到form标签的action属性中的地址 -->
      <button type="reset">重置</button><!-- 清空所有用户输入的内容 -->
    </div>
  </form>
```
###HTML5新增input type（需浏览器支持）
* email
 * 电邮地址，浏览器可以做检查
* url
* number
* tel
* search
* range
 * 一定范围的数据
* color
 * 拾色器
* date picker(date,month,week,time,datetime,datetime-local)
 * 时间选择器

#语义化
用正确的标签描述页面
##语义化的意义
* seo（搜索引擎优化）
* 提高可访问性
* 提高代码可读性
