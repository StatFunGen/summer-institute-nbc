---
title: "网站更新流程"
weight: 90
---

# 网站更新流程

本站采用Markdown维护课程内容，使用Hugo自动生成HTML文件。维护者只需要修改Markdown源文件并推送到GitHub，GitHub Actions会自动生成网站文件。

## 一、更新课程内容

课程介绍、日程、食宿后勤、国家基因库指南等内容统一写在 `content/docs/` 目录下的Markdown文件中。

常见更新位置：

- 课程概览：`content/docs/course/`
- 课程安排：`content/docs/schedule/`
- 食宿与后勤：`content/docs/life/`
- 国家基因库指南：`content/docs/ngb/`

## 二、本地提交修改

修改完成后，在本地仓库执行：

```bash
git add content/docs/ content/_index.md README.md hugo.yaml
git commit -m "更新课程网站内容"
git push
```

## 三、GitHub自动生成HTML

推送到GitHub后，GitHub Actions会自动运行Hugo，把Markdown内容生成HTML文件，并写入 `public/` 目录。

如果 `public/` 中的HTML文件发生变化，GitHub Actions会自动提交一次生成结果，提交信息为：

```text
Build Hugo HTML [skip ci]
```

## 四、不要手动修改public目录

`public/` 是自动生成结果。不要直接修改 `public/` 目录中的HTML文件；下一次构建时这些文件会被Hugo重新生成。

需要改内容时，请修改 `content/docs/` 下的Markdown源文件。

## 五、中文写作规则

本站面向中文课程和中国学员。页面标题、菜单、说明文字、食宿后勤信息、国家基因库指南和维护说明应使用中文。

英文仅用于必要的学术缩写、软件名称、命令名称、文件路径和链接地址，例如GWAS、QTL、TWAS、PRS、Hugo、GitHub、Markdown和HTML。第一次出现重要缩写时，尽量配合中文解释。
