- [LaTeX使用指南](#latex使用指南)
  - [什么是LaTeX？为什么要使用LaTeX？](#什么是latex为什么要使用latex)
  - [环境配置](#环境配置)
    - [安装TeX Live和TexStudio](#安装tex-live和texstudio)
    - [使用overleaf](#使用overleaf)
  - [LaTeX模板下载](#latex模板下载)
  - [宏包](#宏包)
  - [标题，作者，摘要](#标题作者摘要)
  - [正文](#正文)
  - [参考文献管理，引用](#参考文献管理引用)
    - [ref引用](#ref引用)
  - [公式](#公式)
  - [转义字符](#转义字符)
  - [图表](#图表)

# LaTeX使用指南

## 什么是LaTeX？为什么要使用LaTeX？
LaTeX是一个排版工具，它与Word不一样，Word是所见即所得的一个排版工具，即输入是什么样子，最后输出就是什么样子，拥有很高的自由度。但是LaTeX并不是所见即所得的，用户需要输入特定的代码，将其保存在`.tex`的文件里面，然后编译后输出一个pdf文件。

对于对细节不敏感的用户，Word的排版常常会在细节存在问题比如：
- 两段话之间行间距不同、字体不同、标题样式不同等； 
- 对于撰写论文的用户，Word的标题、章节、图表、参考文献等无法自动标号，也很难在正文中引用； 
- 对于有公式输入需求的用户，Word自带的公式不稳定，而公式插件效果常常不好，打一个公式非常费劲。

相比之下，使用LaTeX进行排版，就像是在铺好的轨道上驾驶火车一样。虽然使用上LaTeX没有Word那样自由，但是可以保证你写作的规范性，论文格式的绝对正确性。这使得LaTeX非常适合用于论文排版，只需要用户关注自己具体的论文内容，而不需要额外花时间关注论文的格式问题。简单来说LaTeX相比Word有如下优点：
- 格式是固定的，无需关心论文格式，只需要专注论文内容。
- 输入公式非常方便。
- 期刊被拒之后转成其他期刊的格式也是0成本，只需要将自己的内容复制粘贴到另一个期刊的LaTeX模板就可以完成论文格式的转换。
- 很多计算机顶会只接受LaTeX模板投稿，比如NIPS，他们没有Word模板，只提供LaTeX模板，要想投稿顶会就只能用LaTeX了，当然这个点只在计算机领域有，其他的领域基本上都会提供Word模板以及LaTeX模板。

无论是LaTeX还是Word，其归根结底都只是排版工具，用Word也可以排出LaTeX的效果，用LaTeX也可以排出Word的效果，我们使用LaTeX只是为了更加方便快捷的完成论文写作，而不是纠结于论文格式的调整，是为了提高自己的工作效率，这点需要明白。

## 环境配置
LaTeX是一个需要编译的排版系统，也就是说是需要下载安装其对应的编译器和编辑器的。

### 安装TeX Live和TexStudio
这里就不详细阐述了，网上非常多，可以参考一下这个 -> [最新LaTeX安装详细教程](https://blog.csdn.net/UCB001/article/details/112546694)

TeX Live和TexStudio加起来有好几个G，安装非常慢，大概要一个小时吧。

### 使用overleaf
除了在本地使用LaTeX以外，其实也可以在线使用LaTeX，有一个网站叫[overleaf](https://www.overleaf.com/)，支持在线编辑和编译LaTeX，同时也支持多人同时协助。不过多人同时协助是需要付费的，而且得付美元，免费的版本只能两个账号同时编辑一个项目。不过这里面也有一个bug，那就是一个账号可以被多个人同时登陆，也就是说多人共享一个账号同时编辑项目文件是可行的，建议一个组的同学可以建立一个共享账号，这样就可以多人同时合作了。

overleaf除了可以编辑和多人写作之外还提供了大量其他的LaTeX模板，比如各大高校毕业论文的LaTeX模板，各大期刊，会议的LaTeX模板，其实制作LaTeX模板是一个门槛相对高的活，但是使用LaTeX模板的门槛基本上就低到会打字就行了。


## LaTeX模板下载
上面介绍overleaf的时候提到了可以在overleaf下载模板，但是有一个问题，overleaf上的模板是人传上去的，并不是最新的，也就是说有可能过时了，你要下载最新的准确无误的模板就必须在各大期刊的官网去下载。官网都是有提到这些的，甚至你直接在搜索引擎搜一下xx期刊LaTeX模板结果就出来了。下面分享几个常用的期刊模板下载地址：

- [IEEE旗下的会议期刊模板下载地址](https://template-selector.ieee.org/secure/templateSelector/publicationType)
- [Elsevier旗下期刊模板下载地址](https://www.elsevier.com/authors/policies-and-guidelines/LaTeX-instructions)


## 宏包
通常一个LaTeX的文档结构如下：
```
\documentclass{article}

\usepackage{amsmath, amsthm, amssymb, graphicx}
\usepackage{float}
\usepackage{authblk}
\usepackage{url} 
\usepackage{booktabs}

\title{你的论文标题}

作者信息。。。具体的期刊模板提供作者信息的方式不太一样暂时略过。

\begin{document}

这里是正文. 

\end{document}
```
这里是一个文章的大致结构，正文部分会需要用到图表，url，数学公式等，这个时候就需要使用一些宏包，也就是用`\usepackage{}`导入一些包，例如`\usepackage{booktabs}`就是专门做表的一个包，`\usepackage{graphicx}`就是用来显示图片的一个包。

## 标题，作者，摘要
- 论文的标题很简单，找到`\title{}`，在里面填上就可以了。
- 论文的作者稍微麻烦一些，不同的期刊提供的不太一样，不过也很简单，因为你一看就会了。基本上也就是填空，把作者的名字填到指定的几个空里面，例如这样的`\author[1]{}`，作者的单位同理。
- 摘要也很简单，一看就知道了，一般摘要会是这样的格式：
```
\begin{abstract}
    在这里面填入摘要即可
\end{abstract}
```

## 正文
写正文也是很简单的事情，直接在摘要后面接着就行：
```
\begin{abstract}
    在这里面填入摘要即可
\end{abstract}

\section{Introduction}
    在这里写第一段。

    这里就是第二段了，第一段空一行自动就是一个新的段落。
\section{Methods} % 2
    \subsection{Dataset} % 2.1   
    % 百分号是注释，并不会被编译，一个新的小节就是一个section，小节里面的小节就是subsection，同理类推
    \subsubsection{preprosessing} % 2.2

\section{Results}

\section{Conclusion}

```
正文可以直接在document环境中书写，没有必要加入空格来缩进，因为文档默认会进行首行缩进。相邻的两行在编译时仍然会视为同一段。在LaTeX中，另起一段的方式是使用一行相隔。在正文部分，多余的空格、回车等等都会被自动忽略，这保证了全文排版不会突然多出一行或者多出一个空格。

## 参考文献管理，引用
参考文献我们一般用bibtex来管理，需要新建一个`.bib`的文件，例如：`ref.bib`。然后把需要引用的文献的bibtex格式放到文件里面，这个格式大概长这个样，可以通过谷歌学术获得，也可以通过百度学术之类的，不过最好是谷歌学术，百度学术之类的会有错误，当然更专业的还有通过dblp下载得到：
```
@article{vaswani2017attention,
  title={Attention is all you need},
  author={Vaswani, Ashish and Shazeer, Noam and Parmar, Niki and Uszkoreit, Jakob and Jones, Llion and Gomez, Aidan N and Kaiser, {\L}ukasz and Polosukhin, Illia},
  journal={Advances in neural information processing systems},
  volume={30},
  year={2017}
}
```
然后文末`\end{document}`之前，你要加这两条语句：
```
\bibliographystyle{plain} % plain是LaTeX自带的一个引用风格文件，也可以是其他的期刊自带的文件。
\bibliography{ref} % ref就是咱们的ref.bib文件。
```
之后就可以在正文里面通过`\cite{vaswani2017attention}`引用它了。需要注意的是`@article{vaswani2017attention,`这个`vaswani2017attention`是可以随便改的，只需要你引用的时候`\cite{}`保持一致即可。同时引用多篇：`\cite{1,2,3,4}`。

### ref引用
这个ref其实是可以引用文章内的内容，你在想引用的章节或者图片表格里面加上个，例如：`\label{sec:result}`，然后在正文里面写`In Section~\ref{sec:result}`就可以跳转过去。图片`Figure~\ref{标签名字}`，表格`Table~\ref{表格标签}`。

## 公式
- 行内公式

行内公式通常使用`$..$`来输入，这通常被称为公式环境，例如：
```
若$a>0$, $b>0$, 则$a+b>0$.
```

公式环境通常使用特殊的字体，并且默认为斜体。需要注意的是，只要是公式，就需要放入公式环境中。

- 行间公式

行间公式需要用`$$..$$`来输入：

```
若$a_{1}>0$, $b_{1}>0$, 则
$$
a_{1}+b_{1}>0.
$$
```

若$a_{1}>0$, $b_{1}>0$, 则$a_{1}+b_{1}>0.$


更多情况下我们用这种方法写公式，下面是IoU的数学公式：
```
\begin{equation}
	IoU(N^{(1)}, N^{(2)}) = \frac{\sum_{i=1}^{n}|N_{i}^{(1)} \cap N_{i}^{(2)}|}{\sum_{i=1}^{n}|N_{i}^{(1)} \cup N_{i}^{(2)}|}
\end{equation}
```

$$
IoU(N^{(1)}, N^{(2)}) = \frac{\sum_{i=1}^{n}|N_{i}^{(1)} \cap N_{i}^{(2)}|}{\sum_{i=1}^{n}|N_{i}^{(1)} \cup N_{i}^{(2)}|}
$$

上标可以用`^`输入，下标可以用`_`来输入，上下标只会读取第一个字符，如果上下标的内容较多的话，需要改成`^{}`或`_{}`。

分式可以用\frac{a}{b}显示，即b分之a。

公式这块相对复杂一些，还有很多特殊的数学符号没介绍，但也不需要全部记下来，需要的时候随手一搜就搜到了。

## 转义字符
学会使用转义字符`\`，正文里面很多内容，比如%，_，&，$都有特殊的意思，不能直接被使用，例如76%就打不出来，得写成75\%。其他的同理。

## 图表
- 图片部分

其实图片建议是pdf图片，而不是png或者jpg，因为pdf是矢量图，更加清晰，稍微放大一看就知道pdf更加好。
```
\begin{figure}[htbp]
	\centerline{\includegraphics[width=\columnwidth]{img/img.pdf}} % 图片的路径
	\caption{你的图片标题}
	\label{一个标签，随便写，方便在文章中直接使用\ref引用} 
\end{figure}
```

- 表格部分

我一直是使用的三线表

```
\begin{table}[h]
	\caption{表格标题}
    \label{一个标签，随便写，方便在文章中直接使用\ref引用}
	\centering
	\begin{tabular}{cccc}
		\toprule
		 填写内容 & 填写内容 & 填写内容 & 填写内容 \\
		\midrule	
		 填写内容 & 填写内容 & 填写内容 & 填写内容 \\	
		\bottomrule
	\end{tabular}
\end{table}
```



