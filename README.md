# ife_2017spring

### 学习记录
1. 07/03/2017, task_1_1_1
2. 13/13/2017, task_1_2_1
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
    1. absolute定位，设置top和left为0后, 位置是padding box而不是content box.
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

6. 15/03/2017, task1_5_1
    总结:
    1. section内有4个article和一个aside
    2. aside使用绝对定位,section不设position:relative, 让aside以body为定位点. aside绝对定位后宽度为内容宽度，大约是420px,也可以手动再设置一个宽度.
    3. article设置margin-left:500，让其到body右侧的距离等于article到aside的距离(20)+article宽度(420)+artcile两侧padding(20*2)+article到body右侧的距离(20)
    参考：https://ycitsme.github.io/ife_2017spring/%E5%B0%8F%E8%96%87%E5%AD%A6%E9%99%A2/task_1_3_1.html
