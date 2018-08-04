# wxmodule
微信小程序倒计时和数字输入框组件


![avatar](https://github.com/Takeos/wxmodule/blob/master/wxdemo2.gif)

![avatar](https://github.com/Takeos/wxmodule/blob/master/wxdemo3.gif)

# 倒计时。

## 调用组件

```
<countdown time="5000"></countdown>
```

>其他参数说明：

| 参数 | 描述 | 默认值 |
| ------ | ------ | ------ |
| time | 倒计时的时间，可传毫秒数，日期和数组 | 0 |
| index | 索引值 | 0 |
| showDay | 是否显示天 | false |
| showHour | 是否显示小时 | true |
| showMin | 是否显示分钟 | true |
| showSec | 是否显示秒数 | true |
| bindend | 结束回调 | "" |


# 数字输入框。

## 调用组件
```
<inputnum min="10" max="9999" value="1"></inputnum>
```
>其他参数说明：

| 参数 | 描述 | 默认值 |
| ------ | ------ | ------ |
| min | 最小值 | 1 |
| max | 最大值 | 9999 |
| value | value值 | 1 |
| step | 累加数值 | 1 |
| maxlen | 最多输入位数 | 4 |
| disabled | 禁止使用 | false |
| inpDisabled | 输入框禁止输入	 | true |
| index | 索引值 | 0 |
| bindchange | 改变回调 | "" |


# 单选框和复选框
## 调用
```
<checklist value="1" checked="1" bindchange="changeFn">
    <text>这里是显示的文字</text>
</checklist>
```
>其他参数说明：

| 参数 | 描述 | 默认值 |
| ------ | ------ | ------ |
| type | 设置大小，有s，m，l三种情况 | m |
| index | 索引值 | 0 |
| position | 设置控件的对齐。left和right两种 | left |
| color | 设置颜色 | #FA7346 |
| align | 设置文字的对齐方式。left和right两种 | left |
| margin | 设置控件距离文字的边距	 | 0 20rpx 0 0 |
| disabled | 禁止使用 | false |
| checked | 是否选中 | 0 |
| value | 唯一值 | 0 |
| bindchange | 改变回调 | "" |

>以上参数中algin，margin也可通过内容直接修改。如下：

```
<checklist value="1" checked="1" bindchange="changeFn">
    <view style="text-align: right;margin-left: 20px">可嵌套标签，赋值样式</view>
</checklist>
```

>如果需要多个使用的话，用checkgroup组件包起来，如下：

```
<checkgroup bindchange="changeFn2">
    <checklist value="{{item.value}}" index="{{index}}" disabled="{{item.disabled}}" checked="{{item.checked}}" wx:for="{{items}}" wx:key="{{index}}">{{item.title}}
    </checklist>
</checkgroup>  
```
>checkgroup组件有2个属性：

| 参数 | 描述 | 默认值 |
| ------ | ------ | ------ |
| type | radio,check | check |
| bindchange | 改变回调 | "" |

>如果需要单选框的话，请在checkgroup设置type=”radio”


>组件怎么使用？将组件文件放在项目中。然后再需要引入的页面.json文件里添加如下内容，如果需要修改样式，颜色请自己修改…..


```
{
    "usingComponents": {
        "countdown": "../countdown/index", //路径
        "inputnum": "../inputnum/index",
        "checkgroup": "../checkgroup/index",
        "inputnum": "../inputnum/index"
    }
}
```
