
####背景图片 和 插入图片的差异
- 1 设置的方式不同, 背景图片是通过标签的  `background-image` 属性设置的,每个标签都有一个这个属性,而 插入图片是 通过 img 标签设置的.

 ```
 背景图片
 div{
     background-image: url(abc.jpg);
 }
  插入图片
  <img src="abc.jpg" alt="小图片">
 
  ```

- 2 背景图片仅仅是作为一种装饰,不会占有位置(即 不会影响其他标签的显示), 插入图片会占用一定的空间,影响其他标签的显示.

- 3 背景图片可以通过 **背景定位** 来轻松的设定 背景图片在标签中的位置,而插入图片就不容易设置了,因为没有定位属性.

 ```
 水平方位: left center right
 垂直方位: top center bottom;

 background-position: left bottom;
 或者
 background: url("iamge/abc.png") no-repeat 50px 60px;
 ```

- 4 插入图片的语义比背景图片的语义强,所以开企业开发中,**如果你的图片想被搜索引擎收录,那么推荐使用插入图片<**br>
![](/assets/Snip20180704_2.png)![](/assets/Snip20180704_1.png)
