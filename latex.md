**一个最简单的latex文档**

```latex
\documentclass{article}
\begin{document}
Hello World.
\end{document}
```



**指定文档类型，全局字体大小等**

```latex
\documentclass[12pt]{article}  % 文件开头设置documentclass,12pt大小, article表示整个文档的类别。包括:artical(期刊),report(论文),book(书)等
```



**文档题目放到正中心**

```latex
\title{your doc}    % 设置title
\date{}             % 加上时间，这里设置为{},如果不设置时间为空会默认加上一个时间。

\begin{document}
	
\maketitle         % 显示title

...
\end{document}
```



**换页**

```latex
\newpage
```

**注释**

```latex
%doc   % 使用%进行注释
```

**封面不设置下标**

```latex
\maketitle
\thispagestyle{empty}   % 封面不显示下标

\newpage
\setcounter{page}{1}   % 第二页下标设置为1
  ....
```

**居中**

```latex
\begin{center}   % 居中
your doc
\end{center}
```

**中文支持**

```shell
# 下载安装ctex
https://ctan.org/pkg/ctex下载解压
cd ctex
tlmgr gui
tlmgr install ctex  # 安装
sudo texhash  # 刷新
sudo mktexlsr
texstudio->performance->build->default compile->XeLaTeX
```

```latex
\usepackage{ctex}  % 开头使用ctex
```

**局部字体大小**

```
{\large yourdoc}  % {}括起来，\large表示使用大号字体

% 字体从小到大包括:
\tiny
\scriptsize
\footnotesize
\small
\normalsize
\large
\Large
\LARGE
\huge
\Huge
```

**换行**

```latex
\\   % 换行
```

**首行不缩进**

```latex
\noindent   % 放在首行开始位置表示不缩进
```

**自动生成目录**

```latex
\tableofcontents
```

**章节，分节**

```latex
% article
\section{小节目录}
\section*{不带序号的小节目录}
\subsection{一级标题}
\subsubsection{二级标题}

% book
\chapter{章节目录}
\section{小节目录}
```

**加粗**

```latex
\textbf{}
```



**空格**

```latex
\ 空格  % 用\ 表示空格
```

**自定义语法**

```latex
\newcommand{\new_cmd_name}[param_num]{what_cmd_do}   % 使用newcommand自定义语法，new_cmd_name表示自定义语法名字，{param_num}可选表示参数输入个数，{what_cmd_do}表示自定义语法做什么。

% example: 自定义章节
\newcommand{\isection}[1]{\begin{center}\section*{#1}\end{center}}
```

**使用三方库功能**

```latex
% include third party
\usepackage{ctex}    % 中文字符
\usepackage{fancyhdr}
```

**设置页眉页脚**

```latex
\usepackage{fancyhdr}  % 包含头文件
\fancyhead{}  % 清空页眉
\fancyhead[CE]{Deep Learning}  % 奇数页正中间页眉尾Deep Learning
% 参数:  
% E: Even page
% O: Odd page
% L: Left field
% C: Center field
% R: Right field

\fancyhead[OC]{\leftmark}  % 使用章节标题作为页眉
% leftmark: chapter
% rightmark: section
```

