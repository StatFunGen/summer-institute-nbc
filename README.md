# 第四届大鹏湾统计功能基因组学暑期课程网站

本仓库用于维护第四届大鹏湾统计功能基因组学暑期课程网站。网站使用Hugo和Hugo Book主题生成，面向中文课程和中国学员。

课程内容使用Markdown维护，源文件位于 `content/docs/`。生成后的HTML文件位于 `public/`，由GitHub Actions自动生成并提交回本仓库。本仓库不使用GitHub Pages部署流程。

## 内容目录

- `content/docs/course/`：课程概览、学术内容、组织架构与授课团队。
- `content/docs/schedule/`：五天课程安排。
- `content/docs/life/`：食宿与后勤，包括签到、住宿、吃饭、车辆、上网、饮水和发票。
- `content/docs/ngb/`：国家基因库指南。
- `content/docs/maintenance.md`：网站更新流程。

## 如何更新网站

1. 修改 `content/docs/` 下的Markdown文件。
2. 本地提交并推送：

```bash
git add content/docs/ content/_index.md README.md hugo.yaml
git commit -m "更新课程网站内容"
git push
```

3. 推送到GitHub后，GitHub Actions会自动安装Hugo、生成HTML，并把 `public/` 目录中的生成结果提交回 `main`。
4. 如果看到提交信息 `Build Hugo HTML [skip ci]`，说明HTML已经由自动流程生成。

不要直接修改 `public/` 目录中的HTML文件。`public/` 是自动生成结果，下一次构建时会被覆盖。需要改内容时，请修改Markdown源文件。

## 本地预览

本地已可用 `pixi global install hugo` 安装Hugo。初始化主题后运行：

```bash
git submodule update --init --recursive
hugo server
```

本地生成静态HTML：

```bash
hugo --gc --minify --cleanDestinationDir --noTimes --noChmod --destination public
```

## 中文写作规则

本站页面标题、菜单、说明文字、食宿后勤信息、国家基因库指南和维护说明应使用中文。英文仅用于必要的学术缩写、软件名称、命令名称、文件路径和链接地址，例如GWAS、QTL、TWAS、PRS、Hugo、GitHub、Markdown和HTML。
