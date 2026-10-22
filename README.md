# C 语言入门：从计算机组成到指针

一本用 [ElegantBook](https://github.com/ElegantLaTeX/ElegantBook) 模板排版的 C 语言培训教程，
面向**电控算法组的新同学**，假设读者此前没有编程基础。

- 全书 11 章 + 5 个附录，约 194 页
- 代码严格遵循 **C89/C90** 风格：变量先声明、`for` 里不定义变量、只用 `/* */` 注释
- 每章配有：本章导读、一句话题记、TikZ 图解、完整可编译示例、运行结果、例题与章末习题
- 包含“拔高阅读”与“小心有坑”两类选读/提醒盒子
- 习题答案集中在附录 C

成品：`main.pdf`

## 章节

1. 计算机组成基础
2. 正式上路：顺序结构程序设计
3. 写在分支结构之前：运算符
4. 分支：明辨是非
5. 循环：重复再重复
6. 数组：优雅的数据存取方式
7. 结构体：古希腊掌管分类的神
8. 指针：会者不难
9. 字符串
10. 排序算法
11. 宏定义

附录：

- A. C 语言速查表
- B. 编译、调试与常见错误
- C. 习题参考答案与提示
- D. 术语中英对照
- E. 函数速查（补充）

## 目录结构

```
main.tex                    主文件（导言区、代码盒/提示盒定义、TikZ 样式）
elegantbook.cls             模板类文件（放在根目录，编译时可直接找到）
latexmkrc                   强制使用 XeLaTeX，Overleaf / latexmk 会读取
chapters/
  00-preface.tex            写在前面（学习路线、C89 约定、排版说明）
  ch01-computer.tex         第 1 章 …
  …
  ch11-macro.tex            第 11 章 宏定义
  appendix-a-cheatsheet.tex 附录 A …
  appendix-e-function.tex   附录 E
assets/
  cover.tex / cover.pdf     自定义封面（TikZ 绘制）
  logo.tex / logo.pdf       自定义徽标
vendor/elegantbook/         ElegantBook 原始发行包与 LPPL 许可证
```

## 编译方法

需要 **XeLaTeX**（推荐 TeX Live 或 MiKTeX）。模板使用 `ctex`，`pdfLaTeX` 无法编译。

在项目根目录执行：

```bash
xelatex main.tex
xelatex main.tex      # 第二遍：目录、交叉引用、书签
```

或者：

```bash
latexmk -xelatex main.tex
```

不需要再设置 `TEXINPUTS`：`elegantbook.cls` 已经放在根目录。

### Overleaf

1. 把仓库或 zip 上传到 Overleaf；
2. 在 **Menu → Compiler** 中选择 **XeLaTeX**（如果读取了 `latexmkrc`，通常会自动使用 XeLaTeX）；
3. 直接编译即可。

> 字体说明：`main.tex` 中只有检测到 Consolas 时才把它设为代码字体，因此 Linux / Overleaf 上会自动回退到默认等宽字体，不会因为缺字体而失败。中文由 `ctex` 自动选择本机可用字体（Windows 用宋体/黑体/楷体，Overleaf 用 Fandol）。

> 封面和徽标已经预编译为 PDF，正常情况下不需要重新生成。
> 如需修改，进入 `assets/` 目录执行 `xelatex cover.tex` / `xelatex logo.tex`。

## 本书约定

- 代码使用 C89/C90：声明写在块首，`for` 循环变量在循环外声明，注释只用 `/* */`；
- 代码盒带行号和语法高亮，可直接复制编译；
- `运行结果` 盒展示典型输出，不同平台可能略有差异；
- 蓝色“定义”、绿色“小贴士”、橙色“小心有坑”、蓝灰“C89 约定”、紫色“拔高阅读”；
- 章末“本章练习”的答案见附录 C。

## 许可

正文内容为本项目原创，可自由取用；`vendor/elegantbook/` 下的模板文件版权归
ElegantLaTeX 项目组，遵循其 LPPL 许可（见 `vendor/elegantbook/LICENSE`）。
