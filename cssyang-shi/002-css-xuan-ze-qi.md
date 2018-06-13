
####一、标签选择器

- 1、**什么是标签选择器？**<br>**作用:** <br> 就是根据指定的标签名称,在当前的界面(文件)中找到所有的该名称的标签,然后设置属性.
**格式:**
```
标签的名称{
    属性的名称:属性的值;
}
```
**注意点:**<br>(1)、标签选择器选择的是当前页面中的所有的同名标签,而不能单独选中某一个标签.<br>(2)、标签选择器无论标签藏的有多深都能选中。<br>(3)、只要是HTML中的标签都可以作为标签选择器。


***
***
<br>
####二、id 选择器

- 1、**什么是id选择器?**<br><br>**作用:<br>**根据指定的**id名称** 找到对应的标签,然后设置属性.<br><br>**格式:**
```
#id名称{
    属性名称:属性的值;
}
// 注意:id选择器一定要在id名称前面加 # 号
```
<br> **注意:** <br>(1)、每个html标签都有一个**id**属性,也就是每个标签都可以设置id属性. <br>(2)、同一个html文件中id的名称不能重复.<br>(3)、在编写id选择器时，一定要在id的名称前面加 `#` 号. <br>(4)、id的名称只能由 **字母、数字、和下划线** 组成.且名称不能以数字开头.<br>(5)、id的名称不能是html的标签名,比如:a、p <br>(6)、**在企业开发过程中,一般情况下如果仅仅是为了设置样式,我们不会使用id,因为在前端开发中,id是留给js使用的.**




***
***
<br>
####三、类选择器
- 1、什么是类选择器？<br><br>**作用:**<br>根据指定的 **类名称** 找到对应的标签,然后设置属性.<br> <br>
**格式:**
```
.类名{
    属性名称:数值的值;
}
```
**注意:**
<br>(1)、每个html标签都有一个class属性,也就是每个标签都可以设置class属性. 
(2)、同一个html文件中不同的标签可以有相同的类名称,即类名可以能重复.
(3)、在编写class选择器时，一定要在id的名称前面加 `.` 号. 
(4)、class的名称只能由 字母、数字、和下划线 组成.且名称不能以数字开头.
(5)、class的名称不能是html的标签名,比如:a、p 
(6)、类名 就是用来给某个特定标签设置样式的
(7)、**在html文件中,每个标签可以同时有绑定多个类名,类名与类名之间以空格分开,如下:**

    ```
    // 同一个标签设置(绑定)多个类名
    <p class="className1 className2 className3"> 我是段落 </p>

    3个类名: className1、className2、className3
    ```
    
***
***
<br>
####四、id 选择器和 class 选择器的理解
<br>
#####(一)、id 和 class 的区别 ?
- 1、id 相当于人的身份证，不能重复，class 相当于人的名称可以重复.
- 2、一个html 标签只能绑定一个id名称,可以绑定多个class 名称.

#####(二)、id选择器和 class 选择器的区别 ?
- 1、id 选择器是以 `#` 开头, class 选择器是以 `.`开头.

#####(三)、在企业开发中用 id 还是用 class ？
- 1、一般情况下id 是给js人员使用的,所以除非特殊情况下,否则不要使用id选择器去设置样式.
- 2、在企业开发中一个人员对类的使用,可以看出这个开发的水平.

**注意 !!! !!!:**<br> **以后在开发中尽量把相同的 css 样式抽到一个类名中来,这样做解耦,重复代码最少,如下:**

```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title> css 样式 demo</title>
        <style>
            .colorR{
                color: red;
            }
            .size30{
                font-size: 30px;
            }
            .bottomLine{
                text-decoration: underline;
            }
        </style>
    </head>
    <body>
        // 这样做解耦 而且描述清晰(尽量使用多个 class 的组合,这样优秀)
        <p class="colorR size30">第一段内容</p>
        <p class="bottomLine size30">第一段内容</p>
        <p class="colorR bottomLine">第一段内容</p>
    </body>
</html>

```




***
***
<br>
####五、后代 选择器 

- 1、**什么是后代选择器?** <br><br> **作用:** <br>**找到指定标签的所有特定的后代(儿子、孙子、重孙子 ... ...)标签,设置属性.**<br><br> **格式:**

```
标签名称1 标签名称2{
    属性名:属性值;
}

eg: 
div p{
        color:red;
    }

先找到标签名是:`标签名称1` 的标签,然后再在这个标签下查找所有的名称是 `标签名称2` 的标签,然后给所有的 `标签名称2` 的标签设置属性.
```
**注意:**<br>（1)、后代选择的的标签名之间必须使用空格隔开。<br>（2）、后代不仅仅是儿子，也包括孙子,重孙子... ... 只要是放 某个标签里面的子标签都算.<br>（3)、后代选择器不仅仅可以使用标签的名称，还可以使用其他选择器(比如:id 选择器, 类选择器).如下:
```

#address p{
            color:blue;
        }

再如:

.person p{
            color : red;    
        }
        
再如:
#address .person{

}

再如:
.person .man{
            color:green;
        }

```
等等这些都是可以的.
(4)、后代选择器可以无限往后延伸，比如：
```
div ul li p a {
    color = blue;
}
```




  






 