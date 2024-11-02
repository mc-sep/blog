---
title: Projects - MC-Sep
display: 我的项目
description: 这是我的项目列表。
plum: true
wrapperClass: 'text-center'
projects:
  '当前开发':
    - name: 'MC-Sep Image'
      link: 'https://img.mc-sep.top'
      desc: '一款开源的图片上传软件'
      icon: 'i-material-symbols-drive-folder-upload saturate-0'
    - name: 'MC-Sep Email'
      link: 'https://email.mc-sep.top'
      desc: '免费临时邮箱'
      icon: 'i-material-symbols-drive-folder-upload saturate-0'
---

<!-- @layout-full-width -->

<ListProjects :projects="frontmatter.projects" />

