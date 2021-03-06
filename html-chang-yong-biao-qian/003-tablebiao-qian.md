##一、表格标签 
- 表格标签是一个时代的代表,以前绝大多数的标签都是使用表格标签来实现的.**后来被 div 和 css 取代了**

- 什么是表格标签?
表格标签的作用: 用来给一堆数据添加表格语义
其实表格是一种数据的展现形式,当数据量非常大的时候,表格这种展现形式被认为是最重要最为清晰的一种展现形式.

- 表格标签的格式

```
<table>
    <tr>
        <td>需要显示的单元格数据</td>
    </tr>
    
</table>   
```
    - 在表格标签中一个table代表整个表格,也就是说一对table( `<tablf></table>`)标签就是一个表格. 
    - 一对tr(`<tr> </tr>`)标签就是表格中的一行数据.
    - 一对td (`<td> </td>`)标签代表一行数据中的一列(即 一个单元格).
    
#### 注意:
- **表格标签有个边框属性(`border`),这个属性决定了边框的宽度,默认情况下这个属性的值是0,所以默认情况下看不见表格的边框.**
- **表格标签和列表标签一样,他是组合标签,所以table 标签 和 tr 标签要么一起出现要么不出现,不会单独出现.**




####表格标签的属性
- **宽度和高度的属性**
    - 宽度和高度可以给table标签和td 标签使用,tr 标签是不能使用的.
    - 默认请款下表格的宽高是根据内容的多少决定的。
    - 可以给table 标签的 width 和 height 属性设置来决定整个表格的宽高
    - 给td 标签设置了width 和 height 属性值,在没有个table设置width 和 height 属性的情况下，表格的宽高由 td 的宽高来决定， 如果table 设置了宽高，然后又在td 中设置宽高的话，如果td 中的内容宽高小于table 的宽高，那么以table 的宽高来显示，如果td 的总宽高和td 内容的总宽高大于table 的宽高那么以 td 的总宽高显示，否则以table的宽高显示。


- **水平对齐和垂直对齐的属性**
    - 其中水平标签可以给table标签、tr 标签、td 标签使用，垂直标签只能给tr标签和td标签使用。<br>
    <br>**水平对齐** align=(left right center)
        - table标签添加 align 属性可以控制整个表格在水平方向的对齐方式。注意，table 标签只能设置水平方向的 align 不能设置 垂直方向的 align
        - 给tr 标签设置align可以调整这个行中的各个 td 的对齐方式（要么都左对齐，要么都右对齐，居中对齐等）
        - 给td 标签设置align 可以控制当前单元格的对齐方式，注意，如果在tr 中设置了对齐方式，在td 中也设置了对齐方式，那么表格中的对齐方式以td 为准。
        <br>
    <br>**垂直对齐** valign= （top bottom center）
        - 给tr 设置valign 可以改变当前行的垂直对齐方式
        - 给td 设置vlign ，可以控制当前单元格的垂直对齐方式，如果在tr 和 td 中都设置le valign 属性，那么以td 中的valign 属性值为准。
    
    


- **外边距和内边距的属性** 只能给table标签使用
    - 什么是外边距，内边距？
        - 外边距是单元格与单元格之间的间距外边距（cellspacing），默认情况下单元格和单元格之间的外边距是2px

        - 单元格内部与单元格内容之间的间距是内边距(cellPadding),默认情况下，单元格的内边距是 1px
    - 注意： 修改了内边距和外边距后table 的width 和 height 会发生变化。
    
    
####二、通过table 标签实现细线表格   
- 在表格标签中想通过指定外边距 cellspacing = 0 来实现细线表格是，其实他是将2条线合并为1条，所以看上去很不靠谱

```
// table 的 border 是== 0
  <table border="1" cellpadding="0">

            <tr>
                    <td>张三</td>
                    <td>李四</td>

            </tr>

            <tr>
                    <td>张三</td>
                    <td>李四</td>

            </tr>


        </table>
```
![](/assets/屏幕快照 2018-05-25 下午2.51.58.png)


- 细线表格
    - step1 给table标签设置bgcolor
    - step2 给tr标签设置bgcolor
    - step3 给table 标签设置 cellpacing = 1px
    
    table、tr、td 标签都支持bgcolor

```
    <table bgcolor="black" cellspacing="1px">

        <tr bgcolor="white">
                <td>王五</td>
                <td>王五</td>

        </tr>

        <tr bgcolor="white">
                <td>王五</td>
                <td>王五</td>

        </tr>
    </table>
```
![](/assets/屏幕快照 2018-05-25 下午2.59.38.png)


####三、表格实战
```
<table border="1px" bgcolor="black" cellspacing="1px">

        <!--表格标签中专门有个标签用于设置表格的标题-->
        <!--caption 标签必须写在表格标签内-->
        <!--caption 标签必须写在表格标签的第一行-->
        <!--只要将 caption 标签 写在table标签内，那么标题就会自动 相对于table 居中-->
        <caption>
                <h2> 今日头条</h2>
        </caption>

        <!--在 table 标签中 有个th 标签用于 设置 表格的字段标题 它会自动加粗 -->
        <tr bgcolor="#">
            <th >排名</th>
            <th> 关键词</th>
            <th>趋势</th>
            <th>今日搜索</th>
            <th>最近7日</th>
            <th>关键链接</th>

        </tr>

        <tr bgcolor="white">
            <td>第一列数据</td>
            <td>第二列数据</td>
            <td>第三列数据</td>
            <td>第四列数据</td>
            <td>第五列数据</td>
            <td>第六列数据</td>

        </tr>

        <tr bgcolor="white">
            <td>第一列数据</td>
            <td>第二列数据</td>
            <td>第三列数据</td>
            <td>第四列数据</td>
            <td>第五列数据</td>
            <td>第六列数据</td>

        </tr>

        <tr bgcolor="white">
            <td>第一列数据</td>
            <td>第二列数据</td>
            <td>第三列数据</td>
            <td>第四列数据</td>
            <td>第五列数据</td>
            <td>第六列数据</td>
        </tr>
    </table>
```

![](/assets/屏幕快照 2018-05-25 下午4.16.11.png)




####四、表格标签内容的划分

- 由于表格中存储的数据比较复杂，为了方便管理和以及提升语义。我们可以将表格中的存储数据进行分类。
<br>**表格中的存储数据可以分为4类：**
- 1、表格的标题
- 2、表格的表头信息
- 3、表格的主题信息
- 4、表格的尾页信息

![](/assets/屏幕快照 2018-05-25 下午4.21.17.png)

```
 <table border="1px" bgcolor="black" cellspacing="1px" >

            <caption>表格的标题</caption>

            <thead>
                 <tr bgcolor="white">
                     <th> 列标题 </th>
                     <th> 列标题 </th>
                 </tr>
            </thead>

            <tbody>
                <tr bgcolor="white">

                    <td>内容1</td>
                    <td>内容2</td>
                </tr>
            </tbody>

            <tfoot>
                <tr bgcolor="white">
                    <td>尾部1</td>
                    <td>尾部2</td>
                </tr>


            </tfoot>


        </table>
    
    <!--caption 用于指定表格的标题-->
    <!--thead 用于指定标题的字段-->
    <!--tbody 用于显示表格的内容-->
    <!--tfoot 用于显示表格的尾部-->
    注意： 如果我们没有给table设置 tbody 标签，那么系统会自动设置 tbody 标签
    ```
    
 
####四、单元格合并

```
<table border="1px" bgcolor="black" cellspacing="1px" >

            <caption>表格的标题</caption>

            <thead>
                 <tr bgcolor="white">
                     <th> 列标题 </th>
                     <th> 列标题 </th>
                     <th> 列标题 </th>
                     <th> 列标题 </th>
                 </tr>
            </thead>

            <tbody>
                <tr bgcolor="white">

                    <!--colspan="2" 表示将当前的单元格 看做几个单元格，即合并单元格-->
                    <!--注意： 如果把当前的单元格（td ）看做成多个单元格后，那么需要 在当前的行减少相应个数的单元格-->

                    <td colspan="2">内容1</td>
                    <td>内容1</td>
                    <td>内容2</td>
                </tr>
                <tr bgcolor="white"  >

                    <td  bgcolor="green">内容1</td>
                    <td>内容2</td>
                    <td>内容1</td>
                    <!--多行列合并后，下一行的数据 也许要减少相应个数的单元格-->
                    <td rowspan="2" >内容5</td>

                </tr>
                <tr bgcolor="white"   >

                    <td  bgcolor="green">内容1</td>
                    <td>内容2</td>
                    <td>内容1</td>
                    <!--<td >内容5</td>-->

                </tr>
            </tbody>


        </table>
```
![](/assets/屏幕快照 2018-05-25 下午5.30.51.png)

   
         
    
    












 