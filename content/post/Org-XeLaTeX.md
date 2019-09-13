+++
title = "人文社科类学位论文写作"
date = 2019-07-13T00:00:00+08:00
tags = ["latex", "org-mode"]
categories = ["emacs"]
draft = false
+++

<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]}
});
</script>
<script type="text/javascript" async src="path-to-mathjax/MathJax.js?config=TeX-AMS_CHTML"></script>


## 写作缘由 {#写作缘由}

$\LaTeX$的论文排版无可替代，而学校不会专门教排版设计。 针对人文社科类学位论文写作，从基本的文字编辑，数据分析，进度管理，版本控制到最后的排版设计，笔者写下这篇文章， 希望能够帮助大家完成自己的 毕业论文。 默认读者使用 <i class="fab fa-windows"></i> Windows10操作系统， <i class="fab fa-apple"></i> Mac 原理一样，Linux...<i class="fab fa-linux"></i> 嗯，你应该比我知道的多。


## 文字编辑 {#文字编辑}


### Org-mode 安装 {#org-mode-安装}

注：在 buffer 中，C 代表 <kbd>Ctrl</kbd> 键， M 代表 <kbd>Alt</kbd> 键，RET 代表 <kbd>Enter</kbd>，小写字母就是实际字母。

-   下载[Emacs](https://www.gnu.org/software/emacs/download.html) 26.2，安装最新版 [Org-mode](https://orgmode.org/elpa.html) 9.2.4，官网说的配置文件 **init file** 需要新建：
-   打开 **runemacs.exe** ，<kbd>Ctrl</kbd> <kbd>x</kbd> <kbd>Ctrl</kbd> <kbd>f</kbd> 输入 **.emacs** ，新建完成
-   按照官网介绍操作，安装完成后，<kbd>Alt</kbd> <kbd>x</kbd> org-version，应该就是与官网一致的版本。


### 基本操作 {#基本操作}

参照国外大佬的[视频（提取码：26qz ）](https://pan.baidu.com/s/1p6CRrnt6c0WrROvLW0BjRA )，主要记 **快捷键** （输入字母可以识别，但不是最新的，比如大写字母都改小写了），介绍顺序在[这儿](https://orgmode.org/worg/org-tutorials/org-screencasts/org-mode-google-tech-talk.html)。


### 特殊写作环境 {#特殊写作环境}

写作前，开头加入这段文本:

{{< highlight emacs-lisp>}}
# -*- coding: utf-8 -*-
{{< /highlight >}}

保证你的文字导出时不会乱码。

1.摘要

{{< highlight emacs-lisp>}}
#+begin_abstract
摘要测试
#+end_abstract
{{< /highlight >}}

2.代码

<kbd>Ctrl</kbd> <kbd>c</kbd> <kbd>Ctrl</kbd> <kbd>,</kbd>

默认为verbatim环境， 如果要用 minted 宏包，确认你有安装了Python包pygments，建议安装 **Anaconda** ，然后在 #+begin 前一行加上

{{< highlight emacs-lisp>}}
#+ATTR_LATEX: :options org-latex-minted-options
{{< /highlight >}}


## 数据分析 {#数据分析}

SPSS良心14天试用期够用了，如果你经常要写论文，推荐学习一下 **R** 语言。


## <span class="todo TODO_">TODO </span> 使用 Org-mode 的GTD工作流程 {#使用-org-mode-的gtd工作流程}


## 版本控制 [Git](https://git-scm.com/downloads) （可选） {#版本控制-git-可选}

[廖雪峰的Git教程](https://www.liaoxuefeng.com/wiki/896043488029600)


## 协同写作 {#协同写作}

<kbd>Ctrl</kbd> <kbd>c</kbd> <kbd>Ctrl</kbd> <kbd>e</kbd> 导出utf-8文本，供导师修改（反正排版是最后做的）。


## 排版设计 {#排版设计}

笔者在设计过程中发现Org-mode中用 XeLaTeX 写中文文档很早就有人写配置（添加在 **.emacs** 文件的）了， 现在笔者添加到 [ox-latex.el](https://github.com/Tom007Cheung/Org-XeLaTeX/blob/master/ox-latex.el) 里，然后编译：<kbd>Alt</kbd> <kbd>x</kbd> byte-compile-file（支持 <kbd>TAB</kbd> 键自动补全）， 重新打开 runemacs.exe （推荐添加到桌面快捷方式）就可以使用了。 所有文本写完之后，跳到开头，<kbd>Ctrl</kbd> <kbd>c</kbd> <kbd>Ctrl</kbd> <kbd>e</kbd> <kbd>#</kbd>，输入latex，应该可以看到一下信息：

{{< highlight org>}}
#+latex_class: ctexrep
#+latex_class_options:<默认为[12pt, a4paper],可以自己设置>
#+latex_header:\usepackage{学校 \LaTeX 模板样式（.sty结尾），我用的 ecnu}
#+latex_header_extra:
#+description:
#+keywords:
#+subtitle:
#+title: <默认显示你的文件名>
#+latex_compiler: xelatex
#+date: \today
{{< /highlight >}}

如果有学校封面，title，date可以删掉。

表格，图片一律使用图片导入：<kbd>Ctrl</kbd> <kbd>c</kbd> <kbd>Ctrl</kbd> <kbd>l</kbd> file，选择你的本地图片路径即可。 示例： {{<figure src="https://orgmode.org/img/org-mode-unicorn-logo.png">}}


### 安装 [TeXLive](https://zhuanlan.zhihu.com/p/64555335)（强烈推荐）2019 {#安装-texlive-强烈推荐-2019}

安装完成后，打开你的 **.org** 文件，<kbd>Ctrl</kbd> <kbd>c</kbd> <kbd>Ctrl</kbd> <kbd>e</kbd> <kbd>l</kbd> <kbd>o</kbd>， 即可打开编译好的 **pdf** 文件，当然可以自己改一下 **.tex** 文件，这样排版工作量就会少很多。


## 参考链接 {#参考链接}


### 基于 gbt-7714-2015 格式参考文献编译 {#基于-gbt-7714-2015-格式参考文献编译}


#### [org ref](https://github.com/jkitchin/org-ref) 插件 {#org-ref-插件}

[1] <https://www.reddit.com/r/emacs/comments/4k1lp2/noob_question_how_to_set_locales_and_encoding_for/>

[2] <https://www.cnblogs.com/wangkangluo1/archive/2012/02/04/2337705.html>

[3] <http://www.cnblogs.com/visayafan/archive/2012/06/16/2552023.html>

[4] <https://xiaoguo.net/wiki/org-mode-book.html>

[5] <https://orgmode.org/manual/index.html#SEC_Contents>

[6] <https://orgmode.org/worg/org-tutorials/org-screencasts/org-mode-google-tech-talk.html#sec-2>

[7] <https://zhuanlan.zhihu.com/p/64555335>

[8] <https://github.com/jkitchin/org-ref/blob/master/org-ref.org>

{{<figure src="https://www.adobe.com/content/dam/acom/en/legal/images/badges/PDF_24.png">}} [PDF 版本](Org-XeLaTeX.pdf)下载