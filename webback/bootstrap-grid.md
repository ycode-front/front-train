# bootsctrap 栅格系统

[demo](https://git.oschina.net/szycode/front-train-demo/tree/master/bootstrap-grid?dir=1&filepath=bootstrap-grid&oid=095eea41725031be9c0f29ab7f184675ade8a78a&sha=a6b15154b38c76d989b9c36e85e238a904263acd) (先登录 git.oschina)

[参考](http://v3.bootcss.com/css/#grid)

## 为什么使用 bootstrap 栅格系统

- 快速开发，无需编写css就可以实现布局
- bootstrap 的使用范围非常广
- 相比写 css 问题更少
- 学习成本低

## 响应式

bootstrap 栅格系统可以用来做响应式的开发。但是现在对后台pc的页面一般不做要求，除非客户明确提出这个需求。

并且对java开发人员的也不要求掌握响应式的开发。

## 基本结构

```html
<div class="container">
    <div class="row">
        <div class="col-xs-12">
            这里是内容
        </div>
    </div>
</div>
```

例子 base.html

我们使用的时候一般会固定 container 的宽度。

## 栅格如何正确嵌套

- col 必须放在 row 里面
- 每一个 col 两边都会有 15px padding
    - 如果不需要可以直接设置padding为0
    - 如果不需要可以设置子元素的margin-left 为负数来抵消

```html
<div class="row">
    <div class="col-xs-2">
        这里是内容
    </div>
    <div class="col-xs-10">
        <!-- 将一列中的内容再分成两等分 -->
        <div class="row">
            <div class="col-xs-6">第一等分</div>
            <div class="col-xs-6">第二等分</div>
        </div>
    </div>
</div>
```

例子 nest.html

## 列偏移

使用列偏移可以把一列内容放到指定的位置，但是同时会影响其之后的其他列

```html
<div class="row">
    <div class="col-xs-2">
        <div class="box">占据2个栅格</div>
    </div>
    <div class="col-xs-2 col-xs-offset-2">
        <div class="box">占据2个栅格 偏移两个栅格</div>
    </div>
</div>
```

例子 offset.html

## 栅格排序

- col-xs-push-* 将列向右偏移 n 个栅格
- col-xs-pull-* 将列向左偏移 n 个栅格

使用列排序可以把一列内容放到指定的位置，同时不会对其他列的位置产生任何影响

- 排序和偏移的区别
    - 列偏移会影响其他元素,排序不会
    - 排序会导致列的重叠，类偏移不会

例子 sort.html
