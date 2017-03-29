# ife_2017spring

### 学习记录
[实现效果index](https://ycitsme.github.io/ife_2017spring/)
1. 07/03/2017, task_1_1_1
2. 13/13/2017, task_1_2_1, [issue1](https://github.com/ycitsme/ife_2017spring/issues/1)  
    问题：  
    1. 整个页面分为head, body, foot三个部分。body和head,foot之间有一个margin, 不知道怎么消除，
    > 【于13/03/2017 21:40解决】解决方式：添加一个透明的border(border: 1px rgba(1,1,1,0) solid;)到body中。
    参考：https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing

    2. table中最后一行tfoot的中的分隔符不知道怎么去除
    > 【于13/03/2017 22:22解决】解决方式：
    1.首先去除table的border="1"属性  
    2.在tbody的子td中设置border 然后合并(塌陷)相邻td的border(默认为border-collapse: separate,现设为collapse)
    参考：http://htmlpreview.github.io/?https://github.com/iVickers/IFE2017/blob/master/Task02/index.html

    3. form没有完美实现效果图
    > 【于14/03/2017 22:35解决】解决方式：
    1.将一个label和它对应的输入框或者选择框设置为一个filedset, 这些输入框或选择框设置为一个div,给一个right class
    2.在每个fieldset中, 将label和right class都设置为inline-block,于是它们的宽度都变为内容宽度,lable和right class水平排列
    3.设置label的宽度为40%, 然后右对齐(text-align:right), 上对齐(vertical-align:top), 设置margin
    4.设置包含多行的文本框要使用textarea标签,input标签的type属性没有textarea
    参考：1.http://stackoverflow.com/questions/6262472/multiple-lines-of-input-in-input-type-text 2. https://jplyue.github.io/ife-2017/WEIWEI/TASK2/index.html

3. 14/03/2017, task_1_3_1  
    心得:  
    1. absolute定位，设置top和left为0后, 位置是padding box而不是content box. float: left是移动到content box的最左侧而不是padding box。
    2. 使用absolute和float定位后，div的宽度变为内容宽度,但还是display:block.
    2. 对于span,img这样的inline元素，这是垂直方向的margin无效。
    参考：http://stackoverflow.com/questions/11700985/margin-top-not-working-for-span-element

4. 14/03/2017, task_1_4_1  
    参考：[css half circle](https://codepen.io/xram/pen/thLsk)

5. 14/03/2017, task_1_2_2
    更新：
    解决task_1_2_1的三个问题，其他更新如下
    1. 使用更加语义化的标签header,footer,section,article,aside,figure,figcaption代替div。注意：这些新的语义化标签全是默认display:block的。
    2. 对齐导航栏
    3. 实现导航栏锚点功能
    参考：https://www.w3schools.com/html/html5_semantic_elements.asp

6. 15/03/2017, task_1_5_1
    总结:
    1. section内有4个article和一个aside
    2. aside使用绝对定位,section不设position:relative, 让aside以body为定位点. aside绝对定位后宽度为内容宽度，大约是420px,也可以手动再设置一个宽度.
    3. article设置margin-left:500，让其到body右侧的距离等于article到aside的距离(20)+article宽度(420)+artcile两侧padding(20*2)+article到body右侧的距离(20)
    参考：https://ycitsme.github.io/ife_2017spring/%E5%B0%8F%E8%96%87%E5%AD%A6%E9%99%A2/task_1_3_1.html

7. 16/03/2017, task_1_5_1_float_问题 [issue2](https://github.com/ycitsme/ife_2017spring/issues/2)  
    将task_1_5_1作以下修改从position实现变为float实现两列自适应
    1. 将section中的aside移到section的所有article之上
    2. 将aside的css从position: absolute改为float:right

    问题
    1. aside浮动不正常，增加section的border(如改为5px,本来是1px)之后浮动正常，但是不知道为什么

8. 29/03/2017， task1_6_1
    总结：
    1. 总的结构是body->header, section.about, section.technique, footer
    2. header部分：左侧是logo，右侧是日期，使用绝对定位实现
    3. section.about部分: 左边是三张图片组成的一张图片，右边是一个介绍，坐下是三篇小文章。右侧介绍使用绝对定位，三篇小文章使用float:left,记得在section.about上使用clearfix清除浮动效果.
    ```css
    .clearfix::after {
        content: "";
        clear: both;
        display: table;
    }
    ```
    4. section.techonologe部分: 左边是标题和一篇文章，右边是一张图片标题和一个小模块。左右整体布局使用float. 左侧内部图片浮动效果使用float实现;右侧内部的列表前缀可以通过伪元素(content: "▲";)实现,双引号区域的实现借助text-indent,vertical-align和相对对位，为了解决ul和它父元素的margin collapsing（外边距合并）问题，自己想出了以下方法，通过类似clearfix的伪元素方式在ul前面增加空字符串，并设置不可见。
    ```css
    .clearcollapse::before{
        content: "";
        display: table;
    }
    ```
    左侧内部实现图片周围环绕文字时遇到问题:
        1. 如何实现图像四周环绕排列，并没有float: center这样的元素。float+绝对定位会使float失效，float+相对定位不会影响float周围的元素排列（float周围元素的排列和没有相对定位使相同，相对定位只移动其本身）
    5. footer: 只有一个上边框和网址，使用float:right即可。
