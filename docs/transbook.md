# TransBook — 英语阅读手译本

专为英语阅读理解设计的翻译练习模板。输入英文句子，自动计算并生成合适数量的翻译横线，右侧留出词汇笔记区域。

<div align="center">
  <img src="https://raw.githubusercontent.com/ExBook/TransBook/main/README.IMAGE/preview1.png" width="45%">
  &nbsp;
  <img src="https://raw.githubusercontent.com/ExBook/TransBook/main/README.IMAGE/preview2.png" width="45%">
  <br>
  <img src="https://raw.githubusercontent.com/ExBook/TransBook/main/README.IMAGE/preview3.png" width="45%">
  &nbsp;
  <img src="https://raw.githubusercontent.com/ExBook/TransBook/main/README.IMAGE/preview4.png" width="45%">
</div>

## 功能特点

- **智能横线生成**：`\Sentence` 命令自动测量句子宽度，根据行宽计算所需翻译横线数量，无需手动调整
- **段落自动分组**：`Paragraph` 环境自动标注「第一段」「第二段」……，`reset` 参数可重置段落内句子编号
- **带圈句子编号**：每句前自动生成主题色圆形编号，清晰标记句序
- **词汇手记区**：页面右侧约 60mm 宽的专用笔记区域，浅色填充 + 主题色左边界线，标题「词汇手记」
- **参考译文**：`translation` 环境，`showtrans` 选项一键显示/隐藏译文（采用 box0 吞咽技术，隐藏时零输出）
- **「稿纸手写」风格封面**：左侧 12% 窄主题色竖条 + 右侧英文例句与翻译横线装饰，直接唤起翻译练习体验
- **12 种颜色主题**：封面、句子编号、侧边栏全部跟随主题色切换
- **深色模式**：全局 `darkmode` 选项
- **A4 / B5 纸张**：文档类选项切换
- **外部配置**：`config.tex` 管理品牌文字、主题色、水印等全部设置

---

## 快速开始

```bash
latexmk main.tex      # 编译
latexmk -c            # 清理
```

---

## 文档类选项

| 选项 | 默认 | 说明 |
|------|------|------|
| `a4paper` / `b5paper` | a4paper | 纸张尺寸 |
| `adobe` / `ubuntu` / `mac` / `windows` / `fandol` | fandol | 中文字体集 |
| `printmode` | false | 双面打印 + 装订边距 |
| `online` | false | 封面显示勘误链接 |
| `water` | false | 页面水印 |
| `darkmode` | false | 深色模式 |
| `showtrans` | false | 显示参考译文 |

---

## 配置

所有配置在 `config.tex` 中完成。

### 封面

```latex
\Title{英语阅读手译本}
\Subtitle{阅读逐句翻译练习}
\Author{研小布}
\Motto{Practice makes perfect.}
\UpdateTime{2026.05}
```

### 主题颜色

```latex
\setThemeColor{\purple}    % 12 种可选
```

### 品牌文字

```latex
\FooterText{此手译本由公众号【研小布】排版制作}
\SidebarTitle{词汇手记}
\BrandName{研小布}
```

---

## 段落与句子

```latex
\section{2021 年英语一真题阅读}
\subsection{Text 1 — The Value of Higher Education}

\begin{Paragraph}[reset]
    \Sentence{How does the author view the value of higher education?}

    \Sentence{The financial return on a college degree has become a
    widely debated topic.}

    \Sentence{Recent research suggests that the wage premium for
    college graduates remains substantial.}
    \begin{translation}
        近期研究表明，大学毕业生的工资溢价仍然可观。
    \end{translation}
\end{Paragraph}
```

- `Paragraph` 环境：自动标注「第一段」「第二段」……
- `reset` 参数：重置该段落内句子编号
- `Sentence` 命令：自动测量句子宽度，生成对应数量的翻译横线
- `translation` 环境：参考译文，由 `showtrans` 选项控制显示/隐藏

---

## 工具命令

| 命令 | 说明 |
|------|------|
| `\blankbox` / `\eblankbox` | 中文/英文空括号 |
| `\blankline` | 空白下划线 |
| `\textwater` | 渲染水印文字 |
| `\noreftitle{标题}` | 无索引标题 |

[查看完整示例 →](https://github.com/ExBook/TransBook)
