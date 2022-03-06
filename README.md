# ISE_Weekly

本仓库用于ISE组的周报管理。

## GitHub Action的使用

目前，本仓库存在两个GitHub Action用于使得周报的流程更加自动化。

### New Weekly Action

`New Weekly`在每周一下午4点自动创建周报的模板，也可以通过手动进行触发，但是一般不触发。

### Submit Weekly Action

`Submit Weekly`实现自动编号（附件与内容），自动通过`pandoc`将markdown转化为word，然后生成压缩包。提交后，下载上传至QQ群中即可。

## 周报的编写

### 总体模板

```markdown

<!-- 标题与时间都不需要进行手动修改，由GitHub Action自动生成 -->
---
title: '第X周工作汇报'
date: '202X年X月X日-202X年X月X日'
---

<!-- 只允许使用一级标题和二级标题 -->

# 1 研究工作

本周各方向的具体研究工作完成情况如下：

## 1.1 学习Spring Cloud框架——刘雨晴

本周刘雨晴同学在之前学习的基础之上，进一步学习了Spring Cloud微服务框架，详细了解关于Config、Zuul、Bus等组件，熟悉了微服务架构在实际中所遇到各方面问题及其解决方案。

<!-- 注意该超链接应该如何使用，不需要进行手动的编号 -->
[刘雨晴+学习Spring Cloud框架笔记](刘雨晴+学习Spring Cloud框架笔记.docx)

# 2 工程进展

## 2.1 青岛旅游网站项目——刘雨晴、尚超

本周刘雨晴同学参加青岛旅游网站项目的开发，初步熟悉项目的需求，学习项目开发的前置知识Django框架，同时建立起项目开发的必要环境。

本周尚超同学主要工作是熟悉了青岛旅游项目，搭建项目环境。并且开会讨论了青岛旅游项目的组织时间安排与任务分工。熟悉了Web框架Django的基本结构。

# 3 项目进展

## 3.1 知识图谱技术报告文档——刘雨晴、尚超、佘嘉洛

本周刘雨晴、尚超和佘嘉洛同学编写知识图谱项目中关于知识图谱创建和知识融合的技术现状说明并提出相应的可行技术方案，完成初步版本。

# 4 其它工作

## 4.1 不确定性与质量保障论文搜集——张河、曹壮

本周张河同学与曹壮同学搜集了不确定性与质量保障的相关论文，分类为不确定性对感知分析质量的影响、感知分析不确定性处理、感知分析方法质量提升、普通感知分析方法四大类，在搜集过程中还找到一些其他类的论文，包括不确定性与测试用例、不确定性与需求满足、不确定性与自适应模型等等作为论文储备，可以作为后续的研究。

# 5 下周工作计划

## 5.1 学术方面

+ 佘嘉洛同学继续研究弹性伸缩
+ 刘雨晴同学继续研究微服务监控

## 5.2 工程方面

+ 佘嘉洛同学继续推进631项目
+ 刘雨晴同学继续推进631项目

```

### 时间要求

+ 周日晚上8点以前

### 内容要求

+ 个人研究及调研，学术论文撰写，论文阅读，资料学习等放在研究工作中。
+ 代码开发，架构设计等放在工程进展中。
+ 项目申报，结题，报告撰写，材料准备等放在项目工作中。
+ 做PPT，设计海报等实验室任务或者私活放在其他里。
+ 每人至少有一个研究计划。
+ 添加附件的超链接（使用相对地址）。

不需要写入周报的内容：

+ 老师完成的活。
+ 没有工作量的体力劳动。
+ 和小组完全没关系的杂事。

### 汇总要求

+ 检查周报内容的说法是否准确，是否合理。
+ 是否需要合并人在对全组工作有了解的情况下酌情删减（有些人的东西根本不能放）、增加（有些人干了活没写让他补）、修改（有些人话说不清）或总结（有些事两个年级都有写）。

### 文档结构组织

文档的结构组织采用：月份 + 对应星期的文件夹。

月份：`202x.0x`。
星期：`2020.03.02—2020.03.06`，星期一至星期五。

然而，你并不需要担心，已经通过两个GitHub Action自动化实现。

### 使用Markdown撰写

Pandoc使用的Word模板为`Template`中的`custom-reference.docx`，其中`template.md`为Markdown的模板。

写完了md后，使用如下命令生成word文档

```sh
pandoc input.md --reference-doc=custom-reference.docx -o output.docx
```

当然，你并不需要手动生成。目前已通过GitHub Action实现自动化。
