# How to start document?

## Mkdocs

[MkDocs](https://www.mkdocs.org/ "https://www.mkdocs.org/") is a  **fast** , **simple** static site generator that's geared towards building project documentation.

![mkdocs-logo](./statics/img/mkdocs.png){ width="200" align=right}

### Why Mkdocs?

- Easy to learn
- Easy to use
- Easy to export
- Easy to install

## Mkdocs Material

[Mkdocs Material](https://squidfunk.github.io/mkdocs-material/) is a full theme package for MkDocs, a static site generator geared towards (technical) project documentation.

![mkdocs-material](./statics/img/mkdocs-material-logo.png){ width="200" align=right}

### Why Mkdocs Material?

- Works on all devices
- Fast and lightweight
- Has many plugin
- Pretty and minimal

## How to start?

**step0**: If you don't know about MarkDown format you can see [markdown guide](https://www.markdownguide.org/) and [markdown tutorial](https://www.markdowntutorial.com/) or [github cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

Or you can use [table generator](https://tableconvert.com/markdown-generator) if you want to create table.



**step1**:
You need a md editor.
You can use [VSCode](https://code.visualstudio.com/download) or online editor like [dillinger](https://dillinger.io/) or [stack Edit](https://stackedit.io/)

**step2**:
If you install VSCode, with [md viewer extention](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-office) you can see online edit on your md files.

```sh
pip install mkdocs
```

or more generally in this project:

```sh
pip install -r requirements.txt
```

to install everythings you need (e.g. core, extentions ... )

**step3**:
Clone project from it's repo:

```sh
git clone ....
```

**step4**:
Open root directory of project with VSCode.

## How to see docs?

Run this command in the root of docs project:

```sh
mkdocs serve
```

## How to draw diagram?

In mkdocs you can use diagram. Follow bellow steps:

**step1**: Install draw.io package on your system [like that](https://computingforgeeks.com/install-draw-io-desktop-application-on-ubuntu-debian-fedora/) for rendering to image.

**step2**: Install draw.io VSCode extention from [here](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio) for drawing diagram in VSCode.

**step3**: Include your diagram from drawio file to a md file like [that](https://github.com/LukeCarrier/mkdocs-drawio-exporter/blob/master/README.md#usage):

```md
![My alt text](my-diagram.drawio)
```

now you can see your diagram in mkdocs website export.

## Another how to draw diagram?

You can use [kroki](https://kroki.io/).


## Table

[table gen](https://tableconvert.com/markdown-generator)

[csv to md table](https://github.com/mzjp2/mdtable)