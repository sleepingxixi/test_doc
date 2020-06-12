# Button 按钮

## 引入

在 `app.json` 或 `index.json` 中引入组件，详细介绍见[快速上手](#/quickstart#yin-ru-zu-jian)

``` json
"usingComponents": {
  "spr-button": "components/button/button"
}
```

## 代码演示

### 按钮类型

支持 `default` 、 `primary` 、 `contour` 三种类型，默认为 `default` 

``` html
<spr-button type="primary">主要按钮</spr-button>
<spr-button type="default">默认按钮</spr-button>
<spr-button type="contour">描边按钮</spr-button>
```

### 按钮大小

通过 `size` 属性将按钮设置按钮大小，目前支持 `normal` , `middle` , `mini` 三种尺寸，默认为 `normal` 

``` html
<spr-button>默认大按钮</spr-button>
<spr-button size="middle">中等按钮</spr-button>
<spr-button size="mini">按钮</spr-button>
```

### 禁用状态

通过 `disabled` 属性来禁用按钮，此时按钮不可点击

``` html
<spr-button type="primary" disabled>禁用主要按钮</spr-button>
<spr-button type="default" disabled>禁用默认按钮</spr-button>
<spr-button type="border" disabled>禁用描边按钮</spr-button>
```

### 加大按钮

由 `expand` 字段设置，默认按钮的高度为72rpx，圆角为4rpx，使用 `expand` 字段后，高度为88rpx，圆角为8rpx; 

``` html
<spr-button type="primary" expand>加大主要按钮</spr-button>
```

### 大圆角按钮

由 `radius` 字段设置，默认为小圆角按钮

``` html
<spr-button type="primary" radius>圆角主要按钮</spr-button>
<spr-button size="mini" radius>按钮</spr-button>
```

### 加载按钮

由 `loading` , `loadingType` , `loadingSize` , `loadingColor` , `loadingText` 字段设置，

`loading` 表示是否为带加载的图标按钮，默认为 `false` 

`loadingType` 表示加载的图标的类型，默认为 `segment` 

`loadingSize` 表示加载的图标的大小，默认为 28

`loadingColor` 表示加载的图标的颜色, 默认为 `#969799` 

`loadingText` 表示加载的文字，默认为 加载中...

``` html
<spr-button type="primary" loading>主要按钮</spr-button>
<spr-button type="default" loading>默认按钮</spr-button>
<spr-button type="border" loading>描边按钮</spr-button>
<spr-button type="primary" loading loadingType="mum" loadingColor="white">主要按钮</spr-button>
<spr-button type="border" loading loadingType="mum" loadingColor="green">描边按钮</spr-button>
```

### 功能按钮

可以用来设置特殊用途的，主要包括微信的开放能力 `open-type` 

``` html
<spr-button open-type="getUserInfo" bindgetuserinfo="getInfo">按钮</spr-button>
```

### 自定义按钮

由 `customStyle` 字段设置，可以自定义按钮的样式，包括宽，高，圆角，背景颜色，字体大小，字体颜色。
> 【注意】：如果需要自定义边框，不能通过 `customStyle` 字段设置，需要通过 `customBorder` 设置，否则会导致样式问题。

``` html
<spr-button type="primary" customStyle="width:500rpx;height:300rpx;line-height:300rpx;font-size:50rpx;border-radius:20rpx;">
    自定义按钮
</spr-button>

<spr-button type="border" customBorder="border:1rpx solid blue;">自定义边框按钮</spr-button>
```

## API

### Props

| 参数 | 说明 | 类型 | 默认值 | 版本 |
|-----------|-----------|-----------|-------------|-------------|
| id | 标识符 | *string* | - | - |
| type | 按钮类型， `default` 、 `primary` 、 `contour` | *string* | `default` | - |
| size | 按钮尺寸，可选值为 `normal` , `middle` , `mini` | *string* | `normal` | - |
| disabled | 是否禁用按钮 | *boolean* | `false` | - |
| radius | 是否为大圆角按钮 | *boolean* | `false` | - |
| expand | 是否为加大的按钮 | *boolean* | `false` | - |
| loading | 是否为加载按钮 | *boolean* | `false` | - |
| loadingType | 加载图标类型，前提是选择了设置了 `loading` 属性，加载按钮类型参考 `icon` 组件 | *string* | - | - |
| loadingSize | 加载图标的大小 | *number* | 28 | - |
| loadingColor | 加载图标的颜色 | *string* | - | - |
| loadingText | 加载状态时的文字 | *string* | 加载中... | - |
| customStyle | 自定义按钮的样式，除边框以外 | *string* | - | - |
| customBorder | 自定义边框 | *string* | - | - |
| form-type | 用于 `form` 组件，点击分别会触发 `form` 组件的 `submit/reset` 事件 | *string* | - | - |
| custom-style | 自定义样式 | *string* | - | - |
| open-type | 微信开放能力，具体支持可参考 [微信官方文档](https://mp.weixin.qq.com/debug/wxadoc/dev/component/button.html) | *string* | - | - |
| session-from | 会话来源, open-type="contact"时有效 | *string* | - | - |
| business-id | 客服消息子商户 id | *number* | - | - |
| send-message-title | 会话内消息卡片标题, open-type="contact"时有效 | *string* | 当前标题 | - |
| send-message-path | 会话内消息卡片点击跳转小程序路径, open-type="contact"时有效 | *string* | 当前分享路径 | - |
| send-message-img | sendMessageImg, open-type="contact"时有效 | *string* | 截图 | - |
| show-message-card | 是否显示会话内消息卡片，设置此参数为 `true` ，用户进入客服会话会在右下角显示"可能要发送的小程序"提示，用户点击后可以快速发送小程序消息，open-type="contact"时有效 | *boolean* | `false` | - |
| app-parameter | 打开 APP 时，向 APP 传递的参数 | *string* | - | - |

### Events

| 事件名 | 说明 | 参数 |
|-----------|-----------|-----------|
| bindgetuserinfo | 用户点击该按钮时，会返回获取到的用户信息，回调的detail数据与wx.getUserInfo返回的一致，open-type="getUserInfo"时有效 | - |
| bindcontact | 客服消息回调，open-type="contact"时有效 | - |
| bindgetphonenumber | 获取用户手机号回调，open-type=getPhoneNumber时有效 | - |
| binderror | 当使用开放能力时，发生错误的回调，open-type=launchApp时有效 | - |
| bindopensetting | 在打开授权设置页后回调，open-type=openSetting时有效 | - |
| bindlaunchapp | 打开 APP 成功的回调，open-type=launchApp时有效 | - |

### 外部样式类

| 类名 | 说明 |
|-----------|-----------|
| hover-class | 设置按钮被点击时候的样式 |
| custom-class | 设置按钮的样式 |

### Slot

| 名称 | 说明 |
|-----------|-----------|
| - | 自定义 button 显示内容 |