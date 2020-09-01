# XMUserAgent for Typecho

Typecho 插件，用于在评论区显示用户使用的操作系统、浏览器信息及对应图标。

## 使用说明

1. 解压后修改文件夹名为 XMUserAgent，将插件上传至网站目录的 `/usr/plugins` 下
2. 在 Typecho 后台「插件管理」处启用插件
3. 在需要显示的地方插入以下代码：

```php
<?php $comments->useragent($agentConfig = null); ?>
```
唯一的参数和 Typecho 内置的方法类似，是一个 `Typecho_Config` 或者数组，格式如下
```
array(
    'size' => '12',
    'type' => '1',
    'template' => array(
        '1' => '<img class="icon-ua" src="{{osImage}}" title="{{osTitle}}" alt="{{osTitle}}" height="{{size}}" style="vertical-align:-2px;" />&nbsp;/&nbsp;<img class="icon-ua" src="{{browserImage}}" title="{{browserTitle}}" alt="{{browserTitle}}" height="{{size}}" style="vertical-align:-2px;" />',
        '2' => '{{osTitle}}&nbsp;/&nbsp;{{browserTitle}}',
        'default' => '<img class="icon-ua" src="{{osImage}}" title="{{osTitle}}" alt="{{osTitle}}" height="{{size}}" style="vertical-align:-2px;" />{{osTitle}}&nbsp;/&nbsp;<img class="icon-ua" src="{{browserImage}}" title="{{browserTitle}}" alt="{{browserTitle}}" height="{{size}}" style="vertical-align:-2px;" />{{browserTitle}}',
    ),
)
```
## TODO

- 持续（按需）添加更多浏览器支持，这个可以找原项目的作者，我比较懒。

## 更新日志
- v0.3&emsp;（2020/09/01）修改 UA 调用方式，支持自定义输出格式
- v0.2&emsp;（2019/01/28）将 UA 识别方式本地化，移植了 Wordpress 插件的识别方法。
- v0.1&emsp;（2019/01/27）第一个版本，尚处于测试阶段，请勿用于生产环境。

## 致谢

### 原项目

本项目基于 [hakula](https://github.com/hakula139) 的项目 [UserAgent for Typecho](https://github.com/hakula139/UserAgent-for-Typecho) 进行改进，在此感谢。

### 原原项目

原项目基于 [ennnnny](https://github.com/ennnnny) 的项目 [UserAgent for Typecho](https://github.com/ennnnny/typecho)，在此感谢。

实际上原本我自己博客上使用的就是此插件，但有些地方不太满意，原作者似乎也不再更新了，于是我就打算自己动手丰衣足食，本项目因此诞生。

### Wordpress 插件

> [WP-UserAgent](https://wordpress.org/plugins/wp-useragent)

本项目实质就是将 Wordpress 平台的 UserAgent 插件移植到了 Typecho 平台，感谢原作者 [Kyle Baker](https://www.kyleabaker.com)。

### Iconfont

> [Iconfont](https://www.iconfont.cn) - 阿里巴巴矢量图标库

本项目操作系统、浏览器图标均使用 Iconfont 提供的 SVG 矢量图标，在此感谢。

## 问题反馈


除了在此提 Issue 外，也可以到我的[个人博客](https://doufu.ru/)留言。

希望本插件能帮助到有需要的博主。
