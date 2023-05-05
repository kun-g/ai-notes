---
title: "Commit规范"
description: ""
lead: ""
date: 2022-12-01T10:25:07+08:00
lastmod: 2022-12-01T10:25:07+08:00
draft: false
images: []
menu:
  docs:
    parent: "dev-guide"
    identifier: "commit-312988b83d8b31bf37ec4faaba6c70f0"
weight: 12
toc: true
---

# 规范Commit Message的必要性

一个好的 Commit Message 至关重要：
* 可以使自己或者其他开发人员能够清晰地知道每个 Commit 的变更内容，方便快速浏览变更历史，比如可以直接略过文档类型或者格式化类型的代码变更。
* 可以基于这些 Commit Message 进行过滤查找，比如只查找某个版本新增的功能：git log --oneline --grep "^feat|^fix|^perf"。
* 可以基于规范化的 Commit Message 生成 Change Log。
* 可以依据某些类型的 Commit Message 触发构建或者发布流程，比如当 type 类型为 feat、fix 时我们才触发 CI 流程。
* 自动确定语义化版本的版本号。比如 fix 类型可以映射为 PATCH 版本，feat 类型可以映射为 MINOR 版本。带有 BREAKING CHANGE 的 commit，可以映射为 MAJOR 版本。

# Commit Message规范

## 格式

`type(scope?): subject`

### type

type描述了这次提交的变更类型，常见类型及规范如下图：

![](./images/CommitTypes.png)

#### 对版本号的影响：
- fix - 影响Patch
- feat - 影响Minor
- BREAKING CHANGE/feat! - 修改Major

### scope

描述了修改影响的范围，可以指定多个scope，不同的项目scope会不一样。

### subject

对这次修改的概要描述：这次修改生效后，软件会...

## 举例

### chore: run tests
- 不需要触发CI
- 不用Code Review

### fix(server): send cors headers
- 需要触发CI，甚至可以只编译server相关的部分
- 上线前需要Code Review
- Patch版本号要更新


其它细节参考[约定式提交](https://www.conventionalcommits.org/zh-hans/v1.0.0/)

自动化工具：
- https://github.com/conventional-changelog/commitlint
- https://github.com/llorllale/go-gitlint
- https://github.com/arnaud-deprez/gsemver
- https://github.com/git-chglog/git-chglog