---
cover: ''
tags:
  - elog
  - notion
  - hexo
  - blog
date: '2026-10-29 00:00:00'
urlname: notion-quarto
title: Notion + Quarto
updated: '2026-10-30 11:34:00'
---

# 博客工具

- 写作平台：Notion
- 博客平台：Quarto
- 博客主题：cosmo
- 部署平台：Netlify

# 环境准备


# 博客搭建指南


## 1. Fork模板仓库


[点击 Fork](https://github.com/Wattskemov/Elog-Quarto) 本模板仓库到个人 Github 账号仓库下并 clone 到本地


## 2. 安装依赖


在项目根目录下运行命令安装依赖


```shell
npm install @elog/cli -g
```


## 3. 新建 Elog 本地调试文件


在项目根目录中复制`.elog.env.example`文件并改名为`.elog.env`，此文件将用于本地同步Notion 文档


## 4. 配置 Notion 关键信息


从 [Elog-Quarto](https://app.notion.com/p/ea71ad72e8dd82c9b578818d82a2eca9) 复制数据库到你自己的 Notion 空间，后续对样例文件的修改需要按规则来，如果没有把握就不要随意修改属性，只更新内容和目录部分。


按照[文档提示](https://elog.1874.cool/notion/gvnxobqogetukays#notion)配置 Notion 并获取 `token` 和 `databaseId`，在本地`.elog.env`中写入


```plain text
NOTION_TOKEN=获取的token
NOTION_DATABASE_ID=获取的databaseId
```


在 Notion 里配置 Connection 的信息如下：


![image.png](/images/f29026e4674c2b6f0f8220070b4afe63.png)


## 5.配置代理信息


为保证 Notion API 能顺利访问 Notion 后台接口，需要配置代理信息


```powershell
# http 代理，替换成你的代理地址端口
$env:HTTP_PROXY="http://127.0.0.1:7890"
$env:HTTPS_PROXY="http://127.0.0.1:7890"

# 同步数据
elog sync -e .elog.env
```


## 6.启动 Quarto


数据如果同步正确，你的 Notion 数据都会下载为 Markdown 并存放在 docs 目录，你可以根据 _quarto 的配置信息来修改项目配置以决定你让 Quarto 来如何显示你的效果。


在项目根目录运行 Quarto 启动命令，会自动打开本地博客


```shell
quarto preview
```


## 7. 配置站点


根据 Quarto 配置文档，配置你的博客直到你满意为主，你也可以换别的主题，这里不做演示。


仓库目录下的 docs 目录里的 index.qmd、folder1.qmd 为示例文件，可以任意修改。


总体原则，把动态需要修改的内容尽量放置在 Notion 里，其它 Quarto 工程设置尽量放置在 docs 目录下的工程文件。


这里特意把“首页”和“关于”两个页面拆成了父子页面设计，有关配置和显示式样的内容在代码目录的 docs/index.qmd 和 docs/about.qmd 页面里设置，可以按 Quarto 的要求灵活修改。对于动态需要更新的内容，可以在 Notion 里的“首页”（本质上是 urlname 为 index-subpart）和“关于”（本质上是 urlname 为 about-subpart）页面调整。


## 8. 提交代码到 github


本地访问没问题直接提交所有文件到 Github 仓库即可。


如果 Notion 里的内容有更新，则重新执行第5步，知道内容满意为止。


## 9. 部署到 Netlify


站点可以托管到 Vercel 或是 Netlify 这类静态生成网站，从而保证自动构建。


注册 Netlify 账号并绑定 Github，在 Netlify 导入 该项目，Quarto 比较复杂不同于 Hexo ，需要逐步验证在 Netlify 的部署（有兴趣了解的可以读一下官方文档 [Netlify – Quarto](https://quarto.org/docs/publishing/netlify.html)）。


因为本项目的模版文件为定制化设置，所以请严格按照本教程里的说明来配置：

1. Quarto 比较复杂，所以 build 配置要特别注意，尤其是“Build command”和“Publish directory”，否则很容易失败。

![image.png](/images/c14973556c209209829419a4d2001d8b.png)

1. 在 docs 目录下新建 _publish.yml 文件验证内容能否正常发布到 netlify，该文件的模版如下：

```plain text
- source: project
  netlify:
    - id: "5f3abafe-68f9-4c1d-835b-9d668b892001"
      url: "https://tubular-unicorn-97bb3c.netlify.app"
```

1. 检查发布是否正常：

```plain text
quarto render
quarto publish netlify
```

1. 打开配置的 netlify URL，如果能正常看到站点，就表示一切正常。
2. 检查 docs/netlify.toml 文件，检查里面的 Quarto 版本号是否和你本地一致，只要差别不大应该都一样，如果不一样可以修改为和你本地版本一致，然后提交到 Github 触发自动构建。

# 自定义 Elog 配置


如果想自定义 Elog 配置，可访问 [Elog 文档](https://elog.1874.cool/)


# 博客示例


示例仓库：[https://github.com/Wattskemov/Elog-Quarto](https://github.com/Wattskemov/Elog-Quarto)


博客示例地址：[https://elog-quarto.netlify.app/](https://elog-quarto.netlify.app/)


# Q & A


以下收集到的一些常见疑问，写到下面。


## 为什么要用 Quarto？


这是一个好问题，在有了 Hugo、Hexo 等一系列静态建站工具，为什么还要用 Quarto 呢？


Quarto 的主要场景是科学写作，尤其是在文献交叉引用环节做得很好，语法特别简单利落。而 Hugo、Hexo 这些工具并不原生支持 BibTeX 参考文献引用，就算有一些插件能用上 BibTeX，语法上也没有 Quarto（实际上是 pandoc）舒服。


## 为什么要用 Elog + Quarto？


Notion 或是语雀这些工具对 BibTeX 这些支持不足，无法自动引用参考文献，所以无法直接依赖 BibTeX 来导出生成完整的文章。Zettlr 虽然支持 BibTeX，但是作为一个编辑器来讲，这方面体验做得并不好。


Quarto 本身不提供编辑器，或者说 R Studio 自带的编辑器不好用，我们依然喜欢在 Notion、语雀或是 Joplin 里来写原文，同时标上参考文献等，再导出来用 Quarto 排版生成。这样的流程是实践下来最舒服的，比较专业的记事本软件在写作本身方面确实体感比 Visual Studio Code 这类好太多了。


如果手工从 Notion、语雀或是 Joplin 导出 markdown，又面临一个图片的问题。


而 Elog 恰恰把这些问题都解决了，可以完整的按预期导出文字、图片来供 Quarto 后续自动排版。


Elog + Quarto 这套组合是我实践下来感觉最舒服的。


## 为什么要用 Elog + Quarto + Netlify？

