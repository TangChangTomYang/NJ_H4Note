


***
***
<br>
####十二、序选择器 (选择第几个标签选择器)(下)

**同级别 奇数、偶数位置选择器**

- 1、**同级别 奇数 位置选择器,取出同一级别中 奇数 位置的标签,如果是对应标签就设置属性.**<br><br>**格式:**

    ```
    p:nth-child(odd){
        color:red;
    }
    // odd 是奇数的意思
    ```
    
- 2、**同级别 偶数 位置选择器,取出同一级别中 偶数 位置的标签,如果是对应标签就设置属性.**<br><br>**格式:**

    ```
    p:nth-child(even){
        color:red;
    }
    // even 是偶数的意思
    ```
    
- 3、**同级别 自定义 位置选择器,取出同一级别中 自定义 位置的标签,如果是对应标签就设置属性.**<br><br>**格式:**

    ```
    p:nth-child(xn+y){
        color:red;
    }
    //x 、y 是用户自定义的整数数字
    //n 是同级别中标签的数量
    //如下面标签的例子,这个选择器是这样工作的 n 是同一级标签的个数(此处是15)
    //程序在运行时,n 从1 一次加1,累计加大 n 的最大值(即,此处是15)
    // 此处,3n+1 会一次这样选择 3*0+1=1, 3*1+1=4,3*2+1=7 ... 以此类推
    //找到对应序号上的标签,并判断标签是否是对应的标签,并设置对应的属性
    
    <head> 
        <style> 
            p:nth-child(3n+1){
                color: red;
            } 
        </style> 
    </head>

    <body>

       <p>1</p>
       <p>2</p>
       <p>3</p>
       <p>4</p>
       <p>5</p>
       <p>6</p>
       <p>7</p>
       <p>8</p>
       <p>9</p>
       <p>10</p>
       <p>11</p>
       <p>12</p>
       <p>13</p>
       <p>14</p>
       <p>15</p>

    </body>

    ```
    

    
***
**同级别 同类型 奇数、偶数位置选择器**

- 1、**同级别同类型 奇数 位置选择器,取出同一级别同类型中 奇数 位置的标签,如果是对应标签就设置属性.**<br><br>**格式:**

    ```
    p:nth-of-type(odd){
        color:red;
    }
            // odd 是奇数的意思
```

- 2、**同级别同类型 偶数 位置选择器,取出同一级别同类型中 偶数 位置的标签,如果是对应标签就设置属性.**<br><br>**格式:**

    ```
    p:nth-of-type(even){
        color:red;
    }
    // even 是偶数的意思
    ```


- 3、**同级别同类型 自定义 位置选择器,取出同一级别同类型中 自定义 位置的标签,如果是对应标签就设置属性.**<br><br>**格式:**

    ```
    p:nth-of-type(xn+y){
        color:red;
    }
    //x*(n=(0~同级别同类型的总数))+y
    ```



***
***
<br>
####十三、属性选择器(2种)

- 1、**什么是属性选择器?**<br><br>**作用:**<br>**根据指定的属性名称找到对应的标签,然后设置属性.**<br><br>**格式1:(属性名)**

    ```
    标签名[属性名]{
        color:red;
    }
    
    比如:
    p[id]{
        color:red;
    }
    // 表示是给所有带有 id 属性的 p标签设置属性.
    // 它其实是这样工作的,首先找到所有的p标签
    // 然后再找到的p标签中找出带有id属性的标签,然后设置属性
    ```
    <br><br>**格式2:(属性名=属性值)**
    ```
    标签名[属性=value]{
        color:red;
    }
    
    比如:
    p[class=cc]{
        color:red;
    }
    // 表示,找出所有带有class 属性且属性值等于cc的p标签,设置属性
    ```
    **其实,格式2(标签名[属性=value])的主要应用场景是用于区分input属性,如下:**
    ```
     input[type=text]{
         color: blue;
     }

     input[type=password]{
         color: orange;
     }
    ```
    

