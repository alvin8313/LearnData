---
title: docsify
order: 1
---

[docsify](https://docsify.js.org/#/zh-cn/) 是一个神奇的文档网站生成器，可以快速帮你将 md 文档生成为网站。

## 插件

[docsify 插件列表](https://docsify-preview.vercel.app/#/zh-cn/awesome?id=plugins)

### 待修改

- [ ] [docsify-toc](https://github.com/mrpotatoes/docsify-toc)：给笔记页内部添加目录，不过会让 gitalk 位置出错。参考链接：[Tainacan Wiki](https://tainacan.github.io/tainacan-wiki/#/general-concepts)，[Sureness](https://github.com/dromara/sureness/blob/master/docs/index.html)，[lifeupapp](https://wiki.lifeupapp.fun/zh-cn/#/features/174)。
- [ ] [docsify 笔记类参考](https://notebook.js.org/#/README)：看板娘，多级页面，页面点击效果，网站运行时间。
- [ ] [Live2D Widget](https://github.com/stevenjoezhang/live2d-widget)：在网页中添加 Live2D 看板娘。在 docsify、博客页面添加 Live2D Widget，增加趣味性。
- [x] [docsify-count](https://github.com/827652549/docsify-count)：docsify 的字数和阅读时长插件，不过长年未更新，容易与其他插件位置冲突而无法显示。

### 评论插件

- [giscus](https://github.com/giscus/giscus)：基于 github discussion，近似于论坛。查看 [配置方法](https://blog.csdn.net/duninet/article/details/125280107)。
- [Gitalk](https://github.com/gitalk/gitalk)：基于 github commit，需配置独立库用于存储评论。
- [Valine](https://github.com/xCss/Valine)：可匿名评论，因此不适合国内使用。
- [Gitter](https://gitter.im/)：[boardgame](https://boardgame.io/documentation/#/)，[regauge](https://itchef.github.io/regauge/#/)

## 配置

### [emoji](https://docsify.js.org/#/zh-cn/plugins?id=emoji)

emoji 插件在标题中使用容易出错，建议使用`&#58;`。例如，原本是`:100:`，替换为`&#58;100:`。

实际使用中，我直接复制 emoji，都能正常显示。

## [本地命令](https://github.com/docsifyjs/docsify-cli)

`<path>` 默认为当前路径，可使用子文件夹指定路径，如`./docs`或`docs`。

`[]`为可省略命令区，无实际作用，输出时需要去除。

### Serve 启动

如果你想在电脑上查看 docsify 页面，可执行 serve 架构命令，在本地主机上运行服务。默认本地端口为 3000，可以指定端口。

```bash
docsify serve <path> [--open false] [--port 3000]
```

使用时不要关闭命令终端，否则 serve 也会停止。

### 生成侧边栏

```bash
docsify generate <path> [--sidebar _sidebar.md]
```

generate 命令会遍历指定目录及其子目录的所有 markdown 文件，并生成全路径的 \_sidebar.md。`<path>` 不能省略，需指定子文件夹路径。

如果路径中存在 \_sidebar.md，则会报错。

## 常见问题

### 引用路径

docsify 引用内部文件时，路径会自带添加域名。

例如：指向子文档时，链接是`子文件夹/文档名.md`；指向子文档的小标题时，链接是`子文件夹/文档名？id=小标题`。

### 页面未同步更新

> CDN 默认是有缓存的，如果文件更新，访问的可能不是最新的文件。
>
> 我设置了 routerMode 为 history，使用 CDN 访问非首页，再次刷新会找不到文件。
>
> 如果开启了`relativePath: true`，文件可以找到，但是侧栏上边的标题点击又有点问题。

### GitHub Pages 报错

如果 SSL 链接 404 报错，显示「There isn't a GitHub Pages site here」，则目录中加入`CNAME`文件。