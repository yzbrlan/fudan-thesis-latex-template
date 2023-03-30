# thesis-template

建议使用xetex.

编译顺序:xetex->bibtex->xetex->xetex

更多信息请跳转至：https://github.com/stone-zeng/fduthesis

# 新手上路：在线编译

## 下载模版
将 graduation-thesis 整个文件夹下载下来，打包为zip

## Overleaf在线编译器
将 zip 上传到overleaf在线latex编译器，打开fdthesis.tex主文件进行编译。

具体示例请看：[Overleaf中复旦毕业论文模版 fudan-graduation-thesis](https://www.overleaf.com/read/czjxjrcwrvtx)

# 新手上路：本地编译

1. 安装Latex
2. 安装编辑器vscode
3. 配置环境
4. 下载模板

## 安装Latex

for mac：http://www.tug.org/mactex/

for window： http://www.tug.org/texlive

若本身电脑已经安装了latex，建议更新。注意windows下有ctex和texlive两种类型，建议选择texlive。

## 配置编辑器vscode

下载vscode，官网上下载就行，链接不贴了

## 配置环境

1. vscode上安装插件Latex Workshop，Latex language support。
2. 配置vscode的setting.json文件，**此步骤至关重要！！！**
```
{
  "latex-workshop.latex.recipes": [
    {
      "name": "xelatex",
      "tools": [
        "xelatex"
      ]
    },
    {
      "name": "xelatex -> bibtex -> xelatex*2",
      "tools": [
        "xelatex",
        "bibtex",
        "xelatex",
        "xelatex"
      ]
    }
  ],
  "latex-workshop.latex.tools": [
    {
      "name": "xelatex",
      "command": "xelatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "bibtex",
      "command": "bibtex",
      "args": [
        "%DOCFILE%"
      ]
    }
  ],
  "latex-workshop.latex.autoBuild.run": "never",
  "latex-workshop.view.pdf.viewer": "tab",
  "latex-workshop.latex.clean.fileTypes": [
    "*.aux",
    "*.bbl",
    "*.blg",
    "*.idx",
    "*.ind",
    "*.lof",
    "*.lot",
    "*.out",
    "*.toc",
    "*.acn",
    "*.acr",
    "*.alg",
    "*.glg",
    "*.glo",
    "*.gls",
    "*.ist",
    "*.fls",
    "*.log",
    "*.fdb_latexmk"
  ],
  "explorer.confirmDelete": false,
  "[latex]": {
    "editor.defaultFormatter": "James-Yu.latex-workshop"
  },
  "workbench.colorTheme": "Default Light+",
  "files.associations": {
  
  },
  
}
```


## 下载模板
首先fork这个repo，然后再去把fork出来的repo克隆下来。不要改动此repo！！！！！
打开fdthesis.tex文件，选择xetex -> bibtex -> xetex -> xetex的编译方式即可。