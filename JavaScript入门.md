[TOC]

# JavaScript入门

## 第一部分 JavaScript基础

### 第1章 JavaScript

- A.window 和 document对象

<img src="image/1.A.png">

- B.对象表示法

  - 句点方式

- C.与用户交互

  - ```html
        <script>
            //弹出一个窗口
            alert(document.title)//读取对象属性
            //在body中写入文字
            document.write("this is class one!")
        </script>
    ```

    

### 第2章 创建简单脚本

- A.在Web页面添加JavaScript
  - 方法一：如上，直接写在script中，放在html中
  - 方法二：建立一个js文件，再用，`<script src = "mycode.js"></script>`
    - 中间不得再写内容

- B.代码注释

  - 用c语言方式即可

- C.变量

  - 无论是何种类型变量，均用var类型
  - 运算方式与C一致
    - +（加号）可将字符串加在一起

- D.捕获鼠标事件

  - onClick

    - 鼠标点击产生反应

  - onMouseOver

    - 鼠标在该区域

  - onMouseOut

    - 鼠标离开该区域

  - 应用

    - ```html
      <!DOCTYPE html>
      <html lang="en">
      <head>
          <meta charset="UTF-8">
          <meta http-equiv="X-UA-Compatible" content="IE=edge">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
          <title>Document</title>
      </head>
      <body>
          <!-- 增加一个按钮 点击弹出窗口onclick -->
          <input type="button" onclick="alert('you clicked the button')" value="Click Me">
          <!-- 图片切换 鼠标经过图片显示1.jpg 鼠标离开显示2.jpg -->
          <img src="img/1.jpg" alt="1" onmouseout="this.src = 'img/1.jpg'"
          onmouseover="this.src = 'img/2.jpg  '"
          height="100px" width="100px">
      </body>
      </html>
      ```



### 第3章 使用函数

- A.定义函数
  - function  函数名（） {内容}
    - 别忘了括号
  - 可放在body，或者head中
  - 函数名称必须以字母或下画线开头，可以包含字母、数字和下画线
- B.调用函数
  - 调用函数名即可
  - 可传递多个参数（和其他语言大致相同）
  - 返回值也和其他语言大致相同
- C.匿名函数
  - `var sayhello = function() {alert("sayhello");};`





### 第4章 函数的更多知识

- A.作用域

  - 分两种：
    - 函数作用域
    - 全局作用域
  - 在函数中定义的为局部变量，局部变量不会作用域函数外，但是，函数中可以更改全局变量
  - 关键词this
    - 可调用全局变量
  - 使用let和const
    - let x 可以保证块级变量，仅作用于该花括号内
    - const x 表示，x将无法改变

- B.箭头函数

  - 在匿名函数的基础上更改
  - `var sum = (x,y,z) => alert(x+y+z);`
    - 多个语句可用花括号

- C.默认参数

  - 与python一致

- 代码

  - ```html
    <!DOCTYPE html>
    <html lang="en">
    
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>作用域</title>
    </head>
    
    <body>
        <!-- 4.1作用域 -->
        <!-- <script>
            //全局变量
            var a = 10;
            var b = 10;
            function showVars() {
                //函数变量
                var a = 20; //声明一个新的局部变量 'a' 
                b = 20; //改变全局变量'b'的值
                return "Local variable 'a' = " + a + "\nGlobal variable'b' = " + b;
            }
            var message = showVars();
            alert(message + "\nGlobal variable'a' = " + a + "\nGlobal variable'a' = " + b);
        </script> -->
        <!-- <script>
            var x = 100
            function myfuntion(x){
                var y = x;
                if(x>50){
                    // var y = 10;
                    let y = 10
                    alert("Inner y = "+ y);//10
                }
                alert("Outer y = "+ y)//vay y时显示 10 let 时 100
            }
        </script> -->
        <script>
            // < !--4.2箭头函数-- >
            //一个语句不用花括号，多个语句加花括号
            var sum = (x,y,z) => alert(x+y+z);
        </script>
        <input type="button" onclick="sum(3,4,5)" value="Click Me">
        <!-- 4.3设置默认参数 -->
        <!-- 与python一致 -->
    </body>
    
    </html>
    ```

    



### 第5章 DOM对象和内置对象

- A.与用户交互
  - alert()
    - 弹出一个信息对话框
    - 把字符串作为参数
    - 没有返回值
  - confirm()
    - 弹出模态对话框
    - 字符串为输入
    - 两个按钮，两个返回值
  - prompt()
    - 弹出模态对话框
    - 字符串为输入
    - 用户可输入字符串
    - ok：返回用户输入/默认值      cancel：返回null
- B.根据id选择元素
  - getElementById()
    - 可以得到相应ID的全部属性还有方法
  - innerHTML
    - 读取或者写入元素内部内容
- C.访问浏览器历史记录
  -  JavaScript 里，浏览器的历史记录是用 window.history 对象来表示的
  - 属性：
    - history只有一个属性，就是长度(length)
  - 方法：
    - forward() 可得到历史页表下一个页面（前进）
    - backward可得到历史页表前一个页面（后退）
    - go(n)
      - n正：前进n个页面
      - n负：后退n个页面
      - 也可加字符串
        - 找到第一个符合的

- D.使用location对象

  - <img src="image/5.D.png">
  - 用location对象导航
    - 直接设置href
      - `location.href = 'www.newpage.com'`
      - 转移新的页面，原始页面保留在历史记录中
    - 用replace
      - `location.replace('www.newpage.com')`
      - 新页面在浏览器还有记录中代替旧页面
  - 刷新页面
    - `location.reload()`
      - 不加参数会加在缓存
      - 加参数true不加载缓存
  - 获取浏览器信息：navigator
    - navigator 对象包含了浏览器程序本身的数据

- E.日期和时间

  - ```html
    新建一个包含日期和时间信息的 Date 对象的最简单方法是：
    var mydate = new Date(); 
    变量 mydate 就是一个 Date 对象，其中包含了创建对象时的日期和时间信息。
    JavaScript有很多用于获取、设置和编辑 Date 对象中的数据的方法，下面是一些范例：
    var year = mydate.getFullYear(); //四位数字表示的年份，比如 2012 
    var month = mydate.getMonth(); //数字表示的月份，0～11，0 表示 1 月，以此类推
    var date = mydate.getDate(); //日期，1～31 
    var day = mydate.getDay(); //星期，0～6，0 表示星期日，以此类推
    var hours = mydate.getHours(); //时，0～23 
    var minutes = mydate.getMinutes(); //分，0～59 
    var seconds = mydate.getSeconds(); //秒，0～59
    mydate.getDateString//获得日期的年月日等
    mydate.getTimeString//活动时间类型
    ```

- F.数学方法

  - <img src="image/5.F.png">
  - 常数
    - 

<img src="image/5.F2.png">

- G.关键词with

  - 调用对象是不用指定这个对象

    - ```html
      with (Math) { 
       var myRand = random(); 
       var biggest = max(3,4,5); 
       var height = round(76.35); 
      }
      ```

- 例子

  - ```html
    <!DOCTYPE html>
    <html lang="en">
    
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <style>
            /* td {
                border: 1px solid gray;
                padding: 3px 5px;
            } */
            /* 5时间的例子 */
            p {
                font: 14px normal arial, verdana, helvetica;
            }
        </style>
        <script>
            function telltime() {
            var out="";
            var now=new Date();
            out+="<br />Date: "+now.getDate();
            out+="<br />Month: "+now.getMonth();
            out+="<br />Year: "+now.getFullYear();
            out+="<br />Hours: "+now.getHours();
            out+="<br />Minutes: "+now.getMinutes();
            out+="<br />Seconds: "+now.getSeconds();
            document.getElementById("div1").innerHTML=out;
        }
        </script>
    </head>
    
    <body>
        <!-- 5.1与用户交互 -->
        <!-- <SCript>
            var answer = confirm("do you want to continue?");
            if (answer) {
                var name = prompt("what is your name?","Jone");
                alert("hello "+name);
            }
        </SCript> -->
        <!-- 5.2根据id选择元素 -->
        <!-- <div id = "div1">
            <p>记录学习js的一天</p>
        </div>
        <script>
            //更改盒子里面的内容
            document.getElementById("div1").innerHTML = "<p>我很充实</p>"
        </script> -->
        <!-- 5.4使用navigator -->
        <!-- <script>
            document.write("<table>");
            document.write("<tr><td>appName</td><td>" + navigator.appName + "</td></tr>");
            document.write("<tr><td>appCodeName</td><td>" + navigator.appCodeName
                + "</td></tr>");
            document.write("<tr><td>appVersion</td><td>" + navigator.appVersion
                + "</td></tr>");
            document.write("<tr><td>language</td><td>" + navigator.language
                + "</td></tr>");
            document.write("<tr><td>cookieEnabled</td><td>" + navigator.cookieEnabled
                + "</td></tr>");
            document.write("<tr><td>cpuClass</td><td>" + navigator.cpuClass
                + "</td></tr>");
            document.write("<tr><td>onLine</td><td>" + navigator.onLine + "</td></tr>");
            document.write("<tr><td>platform</td><td>" + navigator.platform
                + "</td></tr>");
            document.write("<tr><td>No of Plugins</td><td>" + navigator.plugins.length
                + "</td></tr>");
            document.write("</table>");
        </script> -->
        The current date and time are:<br />
        <div id="div1"></div>
        <script>
            telltime(); 
        </script>
        <input type="button" onclick="location.reload()" value="Refresh" />
    </body>
    
    </html>
    ```



## 第二部分 JavaScript 编程

### 第6章 数字和字符串

*Javascript 自主识别数据类型*

- A.数值

  - 与其他语言基本相同

- B.全局方法

  - toString()
    - 可加基数换成进制（2，8，16）
  - toExponential(n)
    - 指数表示法
    - 显示为指数形式，n代表小数

- C.Number对象

  - 注意

    - 全局变量方法保持活跃（可直接用isFinite()）
    - 但是有一些有差别
      - isNaN()和Number.isNaN不一样

  - Number.isNaN()

    - 作用

      - 检测是否不是数值类型

      - 是数值返回 false
      - 不是返回true

  - Number.isInteger()

    - 作用
      - 判断是否是整数
      - 是返回true
      - 不是返回false
    - 注意
      - 新版本浏览器可用

  - Number.parseFloat()和Number.parseInt()

    - 作用：强制转化
    - parseFloat()
      - 如第一个是数字，则识别到最后一个数值，并返回
      - 如第一个不是数字，返回NaN
    - parseInt()
      - 一个参数时：作用与parseFloat()相同
      - 两个参数时：第二个代表返回进制

  - Number.isFinite()

    - 作用：判断是否是无穷大
      - 数值返回TRUE
      - 非数值或者数值无穷大（2的53次方）返回false

- D.Number()函数

  - 作用：尽全力返回一个数值，若返回不了，返回NaN

    - ```javascript
      Number(true); // 返回 1 
      Number(false); // 返回 0 
      Number("666"); // 返回 666 
      Number(021-555-3565); // 返回-4103 
      Number('horse'); // 返回 NaN
      ```

调试台：`ctrl+shift+j`可以打开谷歌浏览器调试台

<img src="image/6.D.png">

- E.布尔值
  - true（非零）   false（零）
  - !可以颠倒布尔值
- F.null(空)和undefined(未定义)
