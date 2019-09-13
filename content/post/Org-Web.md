+++
title = "Org-Web"
date = 2019-07-12T00:00:00+08:00
tags = ["org-mode"]
categories = ["emacs"]
draft = false
+++

## Hello World! {#hello-world}


## <span class="todo TODO_">TODO </span> CSS {#css}


### <span class="todo TODO_">TODO </span> #+options: {#options}

html-scripts:nil, html-style:nil, date:nil, creator:t


### <span class="todo TODO_">TODO </span> source code {#source-code}

{{< highlight emacs-lisp>}}
(org-html--translate "Created" info)
(org-html--translate "Updated" info)
{{< /highlight >}}


### <span class="todo DONE_">DONE </span> disable "Validate" {#disable-validate}

In your .emacs file, write it down:

{{< highlight emacs-lisp>}}
(setq org-html-validation-link nil)
{{< /highlight >}}

[This is my search.](https://stackoverflow.com/questions/15134911/in-org-mode-how-do-i-remove-the-validate-xhtml-1-0-message-from-html-export)


### <span class="todo TODO_">TODO </span> MathJaX {#mathjax}