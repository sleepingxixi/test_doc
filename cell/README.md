# Cell 单元格

## 引入

在 `app.json` 或 `index.json` 中引入组件，详细介绍见[快速上手](#/quickstart#yin-ru-zu-jian)

``` json
"usingComponents": {
  "spr-cell": "components/cell/cell",
  "spr-cell-group": "components/cell-group/cell-group"
}
```

## 代码演示

`cell` 单元格主要是以行的形式展示内容，单元格之间默认会设置有分割线。 `cell` 的设计主要分为5个部分，左边图标，左边标题（标题和副标题），内容，右边图标，右边其他项

> `cell` 可以单独使用，也可以结合 `cell-group` 一起使用， `cell-group` 可以为 `cell` 提供上下边框。

### 基础用法

``` html
<spr-cell title="标题" value="文字内容">
</spr-cell>

<spr-cell-group>
    <spr-cell title="标题" value="文字内容">
    </spr-cell>
</spr-cell-group>
```

### 带图标的单元格

左边图标分为大图标和小图标，通过 `size` 来设置， `size` 值可选项为 `big` ， `mini` 。
`size` 为 `big` ， 表示图标大小为 `56rpx` ，线条距离左侧 `90rpx` ；
`size` 为 `mini` 时，表示图标大小为 `40rpx` ，线条距离左侧 `80rpx` ；

> 注意：图标大小决定了底部线条的长度

``` html
<spr-cell leftIcon="sparrow-icon icon-collect" size="mini" title="小图标标题">
</spr-cell>

<spr-cell leftIcon="sparrow-icon icon-collect" size="big" title="大图标标题">
</spr-cell>
```

### 带副标题的单元格

通过 `label` 来设置

``` html
<spr-cell title="大图标标题" label="副标题">
</spr-cell>
```

### 设置内容

通过value可以设置内容

> 建议使用默认槽位进行设置即可

``` html
<spr-cell title="标题" value="文字内容">
</spr-cell>

<spr-cell title="标题" isArrow>
    文字内容
</spr-cell>
```

### 右边箭头

``` html
<spr-cell title="标题" isArrow>
</spr-cell>
```

### 使用槽位

title：表示标题槽位
label：表示副标题槽位
l-icon：表示左边图标槽位
r-icon：表示右边图标槽位
extra：表示最右边的额外补充的槽位

``` html
<spr-cell leftIcon="sparrow-icon icon-address" size="mini">
    <view slot="title" class="slot-title">
        <text class="title-text">标题槽位</text>
        <spr-tag type="contour">标签</spr-tag>
    </view>
    <view slot="label" class="def-label">副标题槽位</view>
</spr-cell>

<spr-cell title="使用槽位自定义左边图标" size="mini">
    <view slot="l-icon" style="margin-right:10rpx;">
        <icon type="success"></icon>
    </view>
    <view class="tip"></view>文字内容
</spr-cell>

<spr-cell leftIcon="sparrow-icon icon-address" size="mini" title="自定义右边图标">
    <view class="tip"></view>自定义右侧图标
    <view slot="r-icon">
        <view class="iconfont iconauto"></view>
    </view>
</spr-cell>

<spr-cell title="槽位extra补充最右侧一张图片" label="测试副标题内容">
    <view slot="extra" class="extra-image">
        <image src="/components/assets/icon.png" />
    </view>
</spr-cell>
```

## API

### cell-group Props

| 参数 | 说明 | 类型 | 默认值 | 版本 |
|-----------|-----------|-----------|-------------|-------------|
| title | 分组标题 | *string* | `-` | - |
| borderless | 是否隐藏外边框 | *boolean* | `false` | - |

### cell Props

| 参数 | 说明 | 类型 | 默认值 | 版本 |
|-----------|-----------|-----------|-------------|-------------|
| leftIcon | 设置左图标名称，可选值见 [Icon 组件](#/icon) | *string* | - | - |
| leftIconColor | 设置左图标颜色 | *string*| - | - |
| size | 设置图标大小， `big` 或者 `mini` ，当 `leftIcon` 有值时，此项必填 | *string* | - | - |
| title | 标题 | *string* | - | - |
| label | 副标题 | *string* | - | - |
| isArrow | 是否有箭头 | *boolean* | `false` | - |
| arrowColor | 箭头颜色 | *string* | - | - |
| value | 单元格的内容 | *string* | - | - |

### Cell Slot

| 名称 | 说明 |
|-----------|-----------|
| default | 自定义 `value` 显示内容，如果设置了 `value` 属性则不生效 |
| title | 自定义 `title` 显示内容，如果设置了 `title` 属性则不生效 |
| label | 自定义 `label` 显示内容，需要设置 `use-label-slot` 属性 |
| l-icon | 自定义左边图标显示内容，如果设置了 `leftIcon` 属性则不生效 |
| r-icon | 自定义右侧图标，如果设置了 `isArrow` 属性则不生效 |
| extra | 自定义最右侧的补充内容 |

### Cell 外部样式类

| 类名 | 说明 |
|-----------|-----------|
| custom-class | 自定义单元格样式 |
| title-class | 标题样式类 |
| label-class | 描述信息样式类 |
| value-class | 右侧内容样式类 |
