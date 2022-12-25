# Git + Netlify 图床

本图床供[个人博客](https://www.pil0txia.com)使用。`BackBlaze B2 + Cloudflare for SaaS + picgo-plugin-s3 + picgo-plugin-compress + FileZilla Pro/CloudBerry Explorer` 方案还是受限于`Cloudflare CDN`的速度，`Netlify`真香。

`PicGo`设定的自定义域名为`https://static.pil0txia.com`

## 博客标题色值

>[首页博客名称颜色更改 · Issue #281 · jerryc127/hexo-theme-butterfly](https://github.com/jerryc127/hexo-theme-butterfly/issues/281)

`hsl(195, 65%, 81%)`（2020-9-9使用）

`hsl(174, 51%, 80%)`

`hsl(184, 51%, 82%)`

`self_title-color_change.css`原放置于`\butterfly\source\css`下，现已上传至https://cdn.jsdelivr.net/gh/PilotXia/imghost/self_title-color_change.css

`hsl(195, 99%, 80%)`（2022-10-7使用）

self_title-color_change.css更名为customTitleColor.css

```css
inject:
  head:
    - <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Pil0tXia/imghost/customTitleColor.css">
```

***

## 2020-7-23_hexo_butterfly_bak_2

>[移动端index_img位置调整 · Issue #280 · jerryc127/hexo-theme-butterfly](https://github.com/jerryc127/hexo-theme-butterfly/issues/280)

### 裁剪首页大图

https://cdn.jsdelivr.net/gh/PilotXia/imghost/picgo/004_clipped_1900p.jpg

感觉人物构图变拥挤了。接下来要对移动端进行测试，还是用原来那张

### 对主题原css更改

`\themes\butterfly\source\css\_layout\head.styl`

```css
#page-header
  position: relative
  width: 100%
  background-color: $light-blue
  background-attachment: scroll
  background-position: center 35%
  background-size: cover
  background-repeat: no-repeat
  transition: all .5s
```

**重点**：`background-position: center 35%;`，原来是`center center`

更改后，`\public\css\index.css`中对应部分变为：

```css
#page-header {
  position: relative;
  width: 100%;
  background-color: #49b1f5;
  background-attachment: scroll;
  background-position: center 35%;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  background-size: cover;
  background-repeat: no-repeat;
  -webkit-transition: all 0.5s;
  -moz-transition: all 0.5s;
  -o-transition: all 0.5s;
  -ms-transition: all 0.5s;
  transition: all 0.5s;
}
```

> 可参考：https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position

***

## 2020-7-23_hexo_butterfly_bak_3

原图片未裁，经压缩。25%，PC端不变，移动端效果很理想。故留用[原比例大图](https://cdn.jsdelivr.net/gh/Pil0tXia/imghost/picgo/004_clipped_1911p.jpg)，弃用[裁剪置中版](https://cdn.jsdelivr.net/gh/PilotXia/imghost/picgo/004_clipped_1900p.jpg)。

```css
#page-header
  position: relative
  width: 100%
  background-color: $light-blue
  background-attachment: scroll
  background-position: 25% center
  background-size: cover
  background-repeat: no-repeat
  transition: all .5s
```

```css
#page-header {
  position: relative;
  width: 100%;
  background-color: #49b1f5;
  background-attachment: scroll;
  background-position: 25% center;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  background-size: cover;
  background-repeat: no-repeat;
  -webkit-transition: all 0.5s;
  -moz-transition: all 0.5s;
  -o-transition: all 0.5s;
  -ms-transition: all 0.5s;
  transition: all 0.5s;
}
```

另，此备份不再保留theme下的diaspora和nexmoe

## 2022-10-7

启用imgbot。关闭preloader加载动画。

~~于注册表`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\OneDrive\EnableODIgnoreListFromGPO`处新建值和名称为`FETCH_HEAD`的字符串以避免git fetch时od的合并冲突。~~无效

## 2022-10-18

* 主题升级至4.4.0。

* [旧版本inject方式更改标题颜色的方法失效](https://github.com/jerryc127/hexo-theme-butterfly/discussions/1084)

* 性能优化~~阉割~~。

* `\themes\butterfly\source\css\_layout\head.styl`中`#page-header`下`&:not(.not-top-img):before`的`background-color:`属性可以调整index_img的亮度，`#site-title`和`#site-subtitle`的`color`属性可以调整标题的颜色。`customTitleColor.css`需要在修改的属性后添加` !important`，故弃用。

## 2022-12-6

jsdelivr国内被sni阻断，已迁移至 `BackBlaze B2 + Cloudflare for SaaS + picgo-plugin-s3 + picgo-plugin-compress + FileZilla Pro/CloudBerry Explorer` 的方案，见[替代JsDelivr？Cloudflare for SaaS + Backblaze B2 免备案自建图床](https://pil0txia.com/post/2022-12-06_cloudflare-for-saas-backblaze-b2/)

## 2022-12-25

她大姨妈