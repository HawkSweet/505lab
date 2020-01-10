#### 1 LaTeX简介
* 维基百科
     >一种基于ΤΕΧ的排版系统，由美国计算机学家莱斯利·兰伯特（Leslie Lamport）在20世纪80年代初期开发，此种格式，即使使用者没有排版和程序设计的知识也可以充分发挥由TeX所提供的强大功能，能在几天，甚至几小时内生成很多具有书籍质量的印刷品。对于生成复杂表格和数学公式，这一点表现得尤为突出。因此它非常适用于生成高印刷质量的科技和数学类文档。这个系统同样适用于生成从简单的信件到完整书籍的所有其他种类的文档。

* LaTeX优点
1、**完美支持数学公式**。
2、**良好的平台通用性** 。目前为止，TeX 几乎在所有的计算机操作系统平台上得到实现。TeX 的源文件可在不同的平台之间自由的交换，而得到的输出是完全相同的。
3、**超常的稳定性**。自从 TeX 出现以来，改动微小，即十几年前的 TeX 文件用现在的 TeX 系统排版得到的结果与十几年前得到的结果是一样的。TeX 系统极少会崩溃，可以处理任意大小的文件，即使你的计算机的内存很少，TeX 也可自如的工作。

* 类比html理解LaTeX
![image](http://liuchengxu.org/blog-cn/assets/images/posts/sketch.png)@w=800h=400

#### 2 准备Tex“引擎”
安装texlive提供LaxTex的编译器和相关组件。
* [清华镜像下载链接](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/) 点进去选择 texlive.iso 文件
#### 3 工具下载
当LaTeX编写工具安装后，配置好LaxTex的编译器路径即可开始使用。
* [Texmaker下载](https://sourceforge.net/projects/texstudio/)、[Tex studio下载](https://www.xm1math.net/texmaker/)、 [在线编写网站](https://www.overleaf.com)
#### 4 安装教程和问题—以Tex studio为例
* 可参考的安装教程，注意有版本的差别 [Win10+Tex live 2018 + Tex studio](https://blog.csdn.net/zaishuiyifangxym/article/details/88170827)
* 安装之后无法找到texlive? 需要配置编译器路径 [参考帖子](http://tieba.baidu.com/p/6006371753?traceid=)

#### 5 论文排版示例
在使用word写好各类论文要素后，就可以使用TexStudio排版。IEEE类journal都提供非常好的模板（文末附下载链接），本节结合某IEEE类期刊LaTeX模板，介绍论文排版的基本要素在TeXStudio中如何编写。
##### 公式
* 行内公式写法
```Tex
勾股定理形式：$a^2+b^2=c^2$
```
* 独立成行写法
```Tex
\begin{equation}
    LaTeX格式的公式
\end{equation}
```
* mathtype6.9
在word中编写公式，可以用自带编辑器排版较好，但公式字体不是Times；或者使用mathtype（后文附百度云下载链接），排版尴尬。
* 推荐神器 mathpix
将手写和截图公式转换成LaTeX格式的公式，在word写作时可以先放在mathType中，或者排版时直接使用，官网免费版本每月50次转换数，[官网下载](https://mathpix.com/)
##### 插图
* 添加插图的写法
```TeX
\begin{figure}[h]\label{fig1}
	\centering
	\includegraphics[scale=0.4]{fig/f1.eps} % fig文件夹下的fi.esp图片，
	\caption{Paper recommendation based on random walk with deviation and behavior model}
\end{figure}
```
* 使用矢量图，因为矢量图在经过任意放大缩小不改变清晰度，矢量图为cdr、eps等格式的文件。设置矢量图所保存路径：
* 如何将visio图转换成.esp [参考](https://jingyan.baidu.com/article/f0e83a259ad7c222e5910107.html)
* 使用coreldraw平面设计软件，设计cdr格式的图（见[本项目的可视化指南-敬请期待...]()）
##### 表格
* 生成表格的写法
```TeX
\begin{table}[h] % table后加*号使表格变通栏
	\caption{Table caption}\label{t1} % 设置表标题和标签
	\setlength{\tabcolsep}{2pt} % 设置列间距
	\begin{tabular}{ll d{1.3} d{1.3} d{1.3} d{1.3} d{1.3} d{1.3}} % 设置列格式
		\hline % 行线
		Dataset&Models&\multicolumn{1}{l}{$\alpha_1$}& % 跨1列flushleft文本为alpha1
		\multicolumn{1}{l}{$\alpha_2$}&
		\multicolumn{1}{l}{$\alpha_3$}&
		\multicolumn{1}{l}{$\alpha_4$}&
		\multicolumn{1}{l}{$\alpha_5$}&
		\multicolumn{1}{l}{$\alpha_6$}\\
		\hline
		CSDS&Linear     &0.164&0.22&0.123&0.3&0.200&0.258\\
			& Logistic  &0.189&0.155&0.157&0.201&0.154&0.144\\
		[6pt] % 空6磅
		KCDS&Linear     &0.155&0.183&0.160&0.218&0.176&0.156\\
			& Logistic  &0.187&0.125&0.151&0.184&0.187&0.125\\
		\hline
	\end{tabular}
\end{table}
```
* [简单表格参考](http://www.modernfig.cn/blog/general/blog_5.html)
* [LaTex表格生成器](http://www.tablesgenerator.com)
##### 参考文献格式
 * 单篇编辑
 在“\document”标签对中加入“thebibliography”标签对例如：
 ```Tex
    \begin{thebibliography}{9}
        \bibitem{r1} B. Newman and E.T. Liu, Perspective on BRCA1, \textit{Breast Disease} \textbf{10} (1998), 3--10.
    \end{thebibliography}
```
 * bibfile.bib文件。
 所有文献都放到同一个文件中，命名为“bibfile.bib”,放在tex文件同一目录。（BibTeX格式可临时从学术搜索引擎下载，或者一次性从文献管理工具中导出，平时读文献时做好参考文献格式的管理。）
  在“\document”标签对中的最后面加入如下代码：
  ```Tex
    \bibliographystyle{plain}
    \bibliography{bibfile}
```
>"plain"为一般格式可选其他如"acm"等，"bibfile"为".bib"格式文件的名称
 * 事先在word中插入参考文献
 可先用zotero管理文献，自动调整引文序号和生成书目。[安装教程](https://zhuanlan.zhihu.com/p/30899762)
#### 6 学习网站和下载链接
* [LaTeX官方文档](https://www.latex-project.org/help/documentation/usrguide.pdf)
* [一个中文排版例子](https://www.jianshu.com/p/2bef8b44f40a)
* [清华毕业论文](https://github.com/xueruini/thuthesis)
* [IEEE投稿模板](https://journals.ieeeauthorcenter.ieee.org/create-your-ieee-article/authoring-tools-and-templates/ieee-article-templates/templates-for-transactions/)
* [LaTex开源小屋](https://www.latexstudio.net/)
* [MathType6.9下载](https://pan.baidu.com/s/1aBuZe3GZLPiODknT7dZE0A)
提取码：bdwu  （配合office2013和visio2013，兼容无忧）

#### 7 指南下载地址
指南放在我的GitHub项目505lab中
* 使用 git命令下载，提倡实验室成员以后多使用GitHub
`git clone https://github.com/HawkSweet/505lab.git`
* 进入我的GitHub直接查看 [HawkSweet](https://github.com/HawkSweet/505lab)

#### 参考资料
* 公众号"AI算法与图像处理"——学习&科研必备的几个实用工具推荐（排版、绘图、查错）
* [LaTex 论文排版(1): Win10 下 LaTex所需软件安装 (Tex live 2018 + Tex studio)](https://blog.csdn.net/zaishuiyifangxym/article/details/88170827)
* [CSDN博文——我的LaTeX入门](https://blog.csdn.net/shujuelin/article/details/79340373)