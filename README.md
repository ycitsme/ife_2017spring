# ife_2017spring

### 学习记录
1. 07/03/2017, task1
2. 13/13/2017, task2  
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

3. 14/03/2017, task_1_3_1  
    心得:  
    1. absolute定位，设置top和left为0后, 位置是padding box而不是content box
    2. 使用absolute定位后，div的宽度变为内容宽度
    2. 对于span,img这样的inline元素，这是垂直方向的margin无效。
    参考：http://stackoverflow.com/questions/11700985/margin-top-not-working-for-span-element
