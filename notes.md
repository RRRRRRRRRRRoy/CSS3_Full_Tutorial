1. 添加行内CSS
    在tag中添加style属性
    例如：
    
    ```HTMl
        <section style='background: #ff1b68; color: white;'>
    ```
    
2. 在head标签内添加CSS
    例如：
    ```HTML
        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="ie=edge">
            <title>uHost</title>
            <link rel="shortcut icon" href="favicon.png">
            <style>
                /* <!-- 将section的背景变为粉红色，字变为白色--> */
                section{
                    background: #ff1b68;
                    color: white;
                }
            </style>
        </head>
    ```
    
3. 通过CSS文件写入央视
    例如：
    ```HTML
        <!-- 在html当中引入 -->
        <link rel="stylesheet" href="main.css">
    ```

4. 更改字体和字体颜色

   例如：

   HTML文件代码：

   ```html
   <head>
     <!-- 引入层叠样式表 -->
     <link rel="stylesheet" href="main.css">
     <!-- 引入google fonts 字体-->
     <link href="https://fonts.googleapis.com/css2?family=Anton&display=swap" rel="stylesheet">
   </head>
   ```

   CSS文件代码：

   ```CSS
   h1{
     	/*字体颜色*/
       color: white;
     	/*google fonts字体*/
       font-family: 'Anton', sans-serif;
   }
   ```

5. 设置选择器选择的对象 (查看01-css-selectors.pdf)

   (1) HTML中的固有标签元素 e,g. h1，CSS中直接使用标签元素名称 h1{}。

   (2) HTML中的类别 e.g. class, CSS中使用.classname{}

   (3) HTML中的ID e.g. id, CSS中使用#ID{}

   (4) HTML中的属性 e.g. <button disabled>, CSS中使用[disabled]{}

   (5) 全局使用*{} （慎用）

6. 选择器的优先级 (查看02-css-specificity.pdf)

   同一个名称的选择器后面的覆盖前面的，可以通过浏览器查看当前的页面使用了哪个CSS

   Inline Style > #ID selector > .Class  :Pseudo-class  [Attribute] > <Tag> / ::Pseudo-element selectors

7. style的继承

   body中的标签可以继承body中的style，

   例如

   HTML代码：

   ```HTML
   <body>
       <main>
           <section id='product-overview'>
               <h1>Get the freedom you deserve.</h1>
           </section>
           <section id='plans'>
               <h1 class='section-title'>Choose Your Plan.</h1>
               <p>Make sure you get the most for your money</p>
           </section>
       </main>
   </body>
   ```

   CSS代码：

   ```CSS
   /* h1 可以从body继承这个字体 */
   body{
       font-family: 'Montserrat', sans-serif;
   }
   ```

   当前的```<p>```没有对应的字体属性，但是body有定义的字体，```<p>```可以对这个进行继承。

8. Combinators

   Combinators是针对class或者ID中的tag的Style进行修改，这种修改方式不同于继承。

   ```CSS
   #product-overview h1{
       color: white;
       font-family: 'Anton', sans-serif;
   }
   .section-title{
       color: #2ddf5c;
       /*使用继承过来的字体*/
       font-family: inherit;
   }
   ```

   当前的例子，是对ID为product-overview中的h1进行style修改。这里可以通过**inherit**属性继承body中的字体。

8. Combinators的几种情况

   Adjacent Sibling

   ​	(a) Elements share the same parents
   
   ​	(b) Second element comes immediately after the first element
   
   ```CSS
   h2 + p{
   	/* 所有紧跟着h2的p的style发生变化 */
     /* 平级并非继承 */
   }
   ```
   
   General Sibling
   
   ​	(a) Elements share the same parents
   
   ​	(b) Second elements come after the first element
   
   ```CSS
   h2 ~ p{
     /* h2后面出现的所有p全部发生变化 */
     /* 平级并非继承 */
     color:red;
   }
   ```
   
   Child Sibling
   
   ​	(a) Second element is a direct child of the first element
   
   ```CSS
   div > p{
     /* 直系继承关系将会更改style，直系子类，不包含孙子类 */
     /* 继承 */
     color:red;
   }
   ```
   
   Descendant Sibling
   
   ​	(a) Second element is a descendant of the first element
   
   ```CSS
   div p{
     /* 不用考虑直系，后代全部更改style，包括子类，孙子类等 */
     /* 继承 */
     color:red;
   }
   ```
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   