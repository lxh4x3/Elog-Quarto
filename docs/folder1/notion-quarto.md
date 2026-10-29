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
updated: '2026-10-29 15:54:00'
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


按照[文档提示](https://elog.1874.cool/notion/gvnxobqogetukays#notion)配置 Notion 并获取 `token` 和 `databaseId`，在本地`.elog.env`中写入


```plain text
NOTION_TOKEN=获取的token
NOTION_DATABASE_ID=获取的databaseId
```


在 Notion 里配置 Connection 的信息如下：


![image.png](/images/f85bea3d4d962ac0dd1e7a28c54d8092.png)


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


数据如果同步正确，你的 Notion 数据都会存放在 docs 目录里，你可以根据 _quarto 的配置信息来修改项目配置以决定你让 Quarto 来如何显示你的效果。


在项目根目录运行 Quarto 启动命令，会自动打开本地博客


```shell
quarto preview
```


## 7. 配置站点


根据 Quarto 配置文档，配置你的博客直到你满意为主，你也可以换别的主题，这里不做演示。


仓库目录下的 docs 目录里的 index.qmd、folder1.qmd 为示例文件，可以任意修改。


总体原则，把动态需要修改的内容尽量放置在 Notion 里，其它 Quarto 工程设置尽量放置在 docs 目录下的工程文件。


## 8. 提交代码到 github


本地访问没问题直接提交所有文件到 Github 仓库即可


## 9. 部署到 netlify


注册 Vercel 账号并绑定 Github，在 Vercel 导入 该项目，Vercel 会自动识别出该 Hexo 项目，不需要改动，直接选择 Deploy 部署。部署完成会有一个 Vercel 临时域名，你也可以绑定自己的域名。


Quarto 比较复杂，所以 build 配置要特别注意，尤其是“Build command”和“Publish directory”，否则很容易失败。


![image.png](/images/6f415bf190261a9e3194642ac10386bc.png)


## 10. 配置 Github Actions 权限


在 Github 仓库的设置中找到 `Actions-General`，打开流水线写入权限`Workflow permissions`


    ![Untitled.png](/images/73243f6663fd601532b508283a3b704e.png)


## 11. 配置环境变量


在本地运行时，用的是`.elog.env`文件中定义的 Notion 账号信息，而在 Github Actions 时，需要提前配置环境变量。


在 Github 仓库的设置中找到 `Secrets  and variables`，新增仓库的环境变量`NOTION_DATABASE_ID`和`NOTION_TOKEN`和`.elog.env`保持一致即可


![Untitled.png](/images/fd99b993627a5f8f7887761eebd41d61.png)


## 12. 自动化部署


当在 Notion 中改动文档后，手动/自动触发 Github Actions流水线，会重新从 Notion 增量拉取文档，自动提交代码到 Github 仓库。


Vercel 会实时监测仓库代码，当有新的提交时都会重新部署博客。如此就实现了自动化部署博客。


整个流程的关键点就在于：如何手动/自动触发 Github Actions


在项目.`github/workflows/sync.yaml`中已经配置了外部 API 触发 Github Actions 事件，所以只需要调用 API 触发流水线即可。


### 手动触发


为了方便，这里提供一个部署在 Vercel 的免费公用的[**ServerlessAPI**](https://github.com/elog-x/serverless-api)，只需要配置好 URL 参数并浏览器访问即可触发流水线


```shell
https://serverless-api-elog.vercel.app/api/github?user=xxx&repo=xxx&event_type=deploy&token=xxx
```


### 自动触发


可在 Notion 中结合 Slack 触发，[参考教程](https://elog.1874.cool/notion/vy55q9xwlqlsfrvk)，这里就不做进一步演示了


# 自定义 Elog 配置


如果想自定义 Elog 配置，可访问 [Elog 文档](https://elog.1874.cool/)


# 博客示例


示例仓库：[https://github.com/LetTTGACO/notion-hexo](https://github.com/LetTTGACO/notion-hexo)


博客示例地址：[https://notion-hexo.vercel.app](https://notion-hexo.vercel.app/)

