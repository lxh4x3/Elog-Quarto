---
cover: ''
tags: []
date: '2026-10-29 17:27:00'
urlname: notion-example
title: Notion示例文章
updated: '2026-10-29 17:27:00'
---

# Notion-Markdown


[Notion示例文章源地址](https://1874.notion.site/Notion-0658ee89cadf4d0e9b6adfbb1d953c70)


## 行内样式


- **加粗**


_斜体_


<u>下划线</u>


删除线


行内代码 `const a = 123`


行内公式，在Vitepress会报错，不做演示


红色的文字


蓝色的文字背景


绿色的块背景


## Basic block（基本块）


## Notion示例文章的子页面

Notion示例文章的子页面


| 表格标题 | 备注              |
| ---- | --------------- |
| 测试1  | 啊大大             |
| 测试2  | `const a = 123` |

- 无序列表
1. 有序列表：事物按规律变化，也有一种不可避免的性质．这种性质就叫做**必然性**
    1. 事物的必然性，是事物本身的性质（我们反对宿命论的是其认为这一切是受神明的支配，而不是反对事物发展中存在的不可避免的性质的事实）
        1. 第三级别列表
        2. 第三级别列表
    2. 其决定于它自己本身发展的情况和周围的条件
        1. 第三级别列表
            1. 第三级别列表
<details>
<summary>折叠块：点击展开【一级】</summary>
<details>
<summary>点击展开【二级】</summary>
<details>
<summary>点击展开【三级】</summary>

内容文本


</details>


</details>


</details>

> 引用块

---


> 👏 标注文本：**Elog 0.4.0-beta.7 发布了！**  
> 开放式跨平台博客解决方案，随意组合写作平台和部署平台  
>   
> 帮助导航👇  
> ❓ [Elog能干什么](https://elog.1874.cool/notion/introduce)  
> 🚀 [快速开始](https://elog.1874.cool/notion/start)


## Media（媒体）


![cover.JPG](/images/10a91945736a3027f2854218fa71c659.JPG)


[bookmark](https://elog.1874.cool)


[46_1677164223.mp4](https://prod-files-secure.s3.us-west-2.amazonaws.com/c021ad72-e8dd-81a2-972a-0003a3cd6079/5999649b-7796-46a0-abd4-2e17b7b607ab/46_1677164223.mp4?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4667ASC5VIO%2F20261029%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261029T093224Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEFAaCXVzLXdlc3QtMiJHMEUCIBKu0t3aYggqdAkT2iCPctzy0HMWnjQ1uGOYFz2%2FPw7qAiEA7ghG9THnv1nWXYNkxiPsKzNacaiPvnr7L5D2h9HIBysq%2FwMIGBAAGgw2Mzc0MjMxODM4MDUiDM4bpYrcRvjDPQ3W7SrcA2%2FlSdyAkuIcNQPgoSPpNmU4nQgmcDDmDWGn9jf23Gj6ofb%2BPetsTylZD9B%2FjGGmYmxGtEHfSEKocgXAjsECLgp8pgebUSRBNpmFuzTmHvbR0DsHyJtSLSIik08UY6Co33dAx40T0i6fdMYVNiIc%2BQDpgiApN2XQbgXFGcxSHai%2B%2FudFSqB3%2F3w99hsbPRecfSaTBC5ceYHV%2FnNYuiytxKxmH9jO00T0iBRtFt9qWXd61QhG4MCK8dyYieuClkd5ISkhfkFOHgOSsrf5EA7GdiphJLiMNxLX6GkqvTx%2BvZXnlr5aM7HyVHH1r5xaUcJR4x6RwcIGoQmzHbVpmOuK0%2Fo7upMi1ey3ems3120JVJBd3mb1v5%2BcG16kI2FzPaOoiqh701C%2F%2F3vxrttFOY%2FbKTsCtnN%2B3k02Ob4nHmJO59E0cDR7yXngxSWJX60NHushMojQlEQQ9hWMfwku82r%2FzqOCwIy8Yi72%2F9LLmwYBIRdUgZa1jK3jcEnbo5y0nK3SxvE5iC7j%2B%2BHUa27bJLDIUOzk8Rk9Q3sU65lt7DEE0lBXHFKP%2F16z0iyOG95wgHVWfORYaFLUvwAMccWIUN5ccQR5mMg1dMQOMPAkqoCrGA%2FsuuhyvnHOMVAlh9nxMMzvi9cGOqUBeiE6pYOMCXQYzD1xcHtKNAHTCVFSyAV4cz9LNA%2BYPo7uThJmrbHRRmR5PaUmRosUZHhYLeHOAyWDXWQk9abfU57Qvm74ZbJrFt8wsf7E36BxfUUtB4RAlbK%2FuJZNnur8P6kjFW6Cy01%2FWVQFfOZYmvxDKhv0H1HYa%2Bp1yHLAfLxCYhd7xymvkNJMjDJlgWvzvgvN91sGqA6JoO2Er40gJpzKYVnL&X-Amz-Signature=bd69f8aa8d5c2fb2074d7f2176f419815bdca28751f0839db1c10353481fa502&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


```python
pwd='123456'
print(f"password={pwd!r}")

## output:
#password='123456'
```


[example.txt](https://prod-files-secure.s3.us-west-2.amazonaws.com/c021ad72-e8dd-81a2-972a-0003a3cd6079/753c8245-2aea-45de-8a5a-509c105f6236/example.txt?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4667ASC5VIO%2F20261029%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261029T093224Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEFAaCXVzLXdlc3QtMiJHMEUCIBKu0t3aYggqdAkT2iCPctzy0HMWnjQ1uGOYFz2%2FPw7qAiEA7ghG9THnv1nWXYNkxiPsKzNacaiPvnr7L5D2h9HIBysq%2FwMIGBAAGgw2Mzc0MjMxODM4MDUiDM4bpYrcRvjDPQ3W7SrcA2%2FlSdyAkuIcNQPgoSPpNmU4nQgmcDDmDWGn9jf23Gj6ofb%2BPetsTylZD9B%2FjGGmYmxGtEHfSEKocgXAjsECLgp8pgebUSRBNpmFuzTmHvbR0DsHyJtSLSIik08UY6Co33dAx40T0i6fdMYVNiIc%2BQDpgiApN2XQbgXFGcxSHai%2B%2FudFSqB3%2F3w99hsbPRecfSaTBC5ceYHV%2FnNYuiytxKxmH9jO00T0iBRtFt9qWXd61QhG4MCK8dyYieuClkd5ISkhfkFOHgOSsrf5EA7GdiphJLiMNxLX6GkqvTx%2BvZXnlr5aM7HyVHH1r5xaUcJR4x6RwcIGoQmzHbVpmOuK0%2Fo7upMi1ey3ems3120JVJBd3mb1v5%2BcG16kI2FzPaOoiqh701C%2F%2F3vxrttFOY%2FbKTsCtnN%2B3k02Ob4nHmJO59E0cDR7yXngxSWJX60NHushMojQlEQQ9hWMfwku82r%2FzqOCwIy8Yi72%2F9LLmwYBIRdUgZa1jK3jcEnbo5y0nK3SxvE5iC7j%2B%2BHUa27bJLDIUOzk8Rk9Q3sU65lt7DEE0lBXHFKP%2F16z0iyOG95wgHVWfORYaFLUvwAMccWIUN5ccQR5mMg1dMQOMPAkqoCrGA%2FsuuhyvnHOMVAlh9nxMMzvi9cGOqUBeiE6pYOMCXQYzD1xcHtKNAHTCVFSyAV4cz9LNA%2BYPo7uThJmrbHRRmR5PaUmRosUZHhYLeHOAyWDXWQk9abfU57Qvm74ZbJrFt8wsf7E36BxfUUtB4RAlbK%2FuJZNnur8P6kjFW6Cy01%2FWVQFfOZYmvxDKhv0H1HYa%2Bp1yHLAfLxCYhd7xymvkNJMjDJlgWvzvgvN91sGqA6JoO2Er40gJpzKYVnL&X-Amz-Signature=e606e3c9ff167e871d7e3fe2e67ea120dac364ac584c26c950b9990d3e496c9f&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


## DataBase（数据库）


数据库


## AI block


API不支持，会报错`Block type ai_block is not supported via the API.`


## Advanced block（高级块）


$$
f\left(\left[\frac{1+\{x, y\}}{\left(\frac{x}{y}+\frac{y}{x}\right)(u+1)}+a\right]^{3 / 2}\right)\tag{行标}
$$


Notion示例文章的同步块


# 折叠一级标题


    ## 折叠二级标题


        折叠内容


两列分栏（左）

- [ ] 左侧书写

两列分栏（右）

- [ ] 右侧书写

```mermaid
graph LR;
Mermaid思维导图-->思维导图
Mermaid思维导图-->研发
```


@Anonymous 


[Untitled](https://app.notion.com/p/f478ef37c82a41f1b7a59c195b043831) 


2023-04-26 


🚀🔥🐸


## Embeds（嵌入）


嵌入网页


[embed](https://elog.1874.cool)

