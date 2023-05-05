---
title: "分支规范"
description: ""
lead: ""
date: 2022-12-01T09:03:35+08:00
lastmod: 2022-12-01T09:03:35+08:00
draft: false
images: []
menu:
  docs:
    parent: "dev-guide"
    identifier: "branch-070e3b074b7df092d2f12406a826b093"
weight: 11
toc: true
---

# 分支分类

有以下几种：
- main
- develop
- feature/*
- hotfix/*

## 主干分支：main

- 用于生成生产版本
- 只有Owner有提交权限，其他人只能通过MR/PR来提交代码
- 通过验收的功能分支可以合并
- 通过验收的缺陷分支可以合并
- 不接受其它类型的合并请求

## 开发分支：develop

- 用于开发阶段做集成测试
- 所有人都可以直接提交代码
- 生成测试版本

## 功能分支：feature/*

- 用于功能开发
- 一般来说，参与该功能开发的人可以提交代码
- 完成后，合并到develop和main分支

## 缺陷分支：hotfix/*

- 用于修复线上问题
- 完成后合并到main分支和develop分支
