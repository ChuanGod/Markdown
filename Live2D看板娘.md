# 在博客园中添加Live 2D 看板娘

## 以下部分为最简操作

直接在设置-页脚HTML处添加如下代码：

````javascript
<script type="text/javascript" charset="utf-8" src="https://files.cnblogs.com/files/liuzhou1/L2Dwidget.min.js"></script>

<script>
  L2Dwidget.init({
        "model": {
            //hibiki-jk妹  koharu-水手服妹妹  tsumiki-绿头发红袜子小妹妹  wanko-可爱小狗
　　　　　　　jsonPath: "https://unpkg.com/live2d-widget-model-koharu@1.0.5/assets/koharu.model.json",
            "scale": 1
        },
        "display": {
            "position": "left", //模型的表现位置
            "width": 150,  //模型的宽度
            "height": 350, //模型的高度
            "hOffset": 30,
            "vOffset": -65,
        },
        "mobile": {
            "show": true,
            "scale": 0.5
        },
        "react": {
            "opacityDefault": 0.7,  //模型默认透明度
            "opacityOnHover": 0.2
        }
    });
</script>
````

半分钟的时间，立马拥有炫酷看板娘！！！

![看板娘](https://s1.ax1x.com/2023/08/24/pPYjIDf.png)

>参考链接：
>	[博客园添加live2d看板娘](https://www.cnblogs.com/GoodMemoryBlog/p/14279625.html "博客园添加live2d看板娘")