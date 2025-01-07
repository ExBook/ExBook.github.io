# 如何使用
1. 配置本地 Latex 环境（或直接使用Overleaf）
2. 拷贝此项目到本地（或 overleaf）

注意：使用此项目需要一点 Latex 基础！

# 项目结构说明
* `ExBoook.cls`：ExBook 文档类，不用管，也不要随便修改；
* `config.tex`：配置文件，在此文件中详细设置页眉、页脚、封面、主题颜色等；
* `main.tex`：文档内容源文件；
* `contents`文件夹：
    * `content_type_one.tex`：制作文字录入型刷题本所要录入的内容（对应 `main.tex` 重的 `\include{contents/content_type_one}`）；
    * `content_type_two.tex`：制作截图型刷题本所要录入的内容（对应 `main.tex` 重的 `\include{contents/content_type_two}`；
    * `pre.tex`：“声明”部分；
* `img` 文件夹：存放项目图片（封面、水印等）
* `fig` 文件夹：存放文字录入型刷题本的题目插图
* `splitImg` 文件夹：存放截图型刷题本的所有题目图片

注：`main.tex` 中，制作文字录入型刷题本时，只需要保留`\include{contents/content_type_one}`；制作截图型刷题本时，只需要保留`\include{contents/content_type_two}`。