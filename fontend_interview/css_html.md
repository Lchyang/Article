## html 面试题

### 如何理解html语义化？
1. 让人可以更好的读懂（增加可读性）
2. 让机器可以更好的读懂（SEO）

### 默认情况下哪些是html标签使块级元素哪些是内联元素？
1. display:block/table div h1 table ul ol li p 等
2. display:inline/inline-block span img input butoon 等

## css 面试题

### 布局
#### 盒模型的宽度如何计算
1. offsetWidth = (content+padding+border) 没有 margin
2. box-sizing = border-box 时 width 的值 就表示的是 offsetWidth 的值

#### margin 纵向重叠的问题
1. 相邻元素得margin-top 和 margin-bottom 会重叠
2. 空元素的的<p></p>的 margin 会被忽略

#### margin 负值的情况
1. margin-top margin-left 负值的时候元素向上，向左移动
2. margin-right负值 右侧元素左移自身不受影响 margin-bottom 负值 下面元素向上移动自身不受影响

#### BFC的理解与应用
##### 什么是BFC? 如何应用
1. Block format context 块级格式化上下文， 一块独立的渲染区域，内部元素得渲染不会影响到边界以外的元素
##### 形成BFC 的条件
1. float 不是 none
2. position 是 absolute fixed 
3. overflow 不是 visible
4. display flex inline-block 等
##### BFC 的常见应用
1. 清除浮动
#### float布局问题，以及clearfix
##### 圣杯布局和双飞翼布局的目的
1. 三栏布局，中间布局最先被加载和渲染（内容重要)
2. 两侧内容固定，中间内容随着宽度自适应
3. 一般用于pc网页
技术总结
1. 使用float布局
2. 两侧使用margin负值，以便中间内容的横向扩展
3. 防止中间内容被两侧覆盖，一个用padding,一个用margin
#### flex 画色子

### 定位
#### absolute relative 分别根据什么来定位
#### 居中对齐有哪些实现方式(常见)

### 图文样式
#### line-height继承的问题

### 响应式
#### rem是什么？和em px 的对比
#### 如何实现响应式


### css3
#### css3动画