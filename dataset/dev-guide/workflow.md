---
title: "研发流程"
description: ""
lead: ""
date: 2022-12-01T07:39:26+08:00
lastmod: 2022-12-01T07:39:26+08:00
draft: false
images: []
menu:
  docs:
    parent: "dev-guide"
    identifier: "workflow-56924cde42aa3a5a42ecb12d6be1ab69"
weight: 1
mermaid: true
toc: true
---

# 总流程
```mermaid
flowchart LR
  需求阶段-->设计阶段
  设计阶段-->开发阶段
  开发阶段-->验收阶段
  验收阶段-->发布阶段
  发布阶段-->运营阶段
```

# 需求阶段
```mermaid
flowchart LR
  需求收集-->需求梳理
  需求梳理-->需求内审
  需求内审-->需求会
```

阶段产出：
- 产品：产品文档、交互设计
- 测试：测试用例

# 设计阶段
```mermaid
flowchart LR
  UI设计-->UI评审会
  程序设计-->技术评审会
```

阶段产出：
- 产品：多语言表
- UI：UI设计稿
- 测试：测试用例
- 开发：API文档、技术文档
- 项目经理：研发排期表

# 开发阶段
```mermaid
flowchart LR
  功能开发-->程序自测
  功能开发-->单元测试
```

阶段产出：
- 开发：程序、自测报告、部署文档

# 验收阶段
```mermaid
flowchart LR
  功能测试-->集成测试
  集成测试-->压力测试
  集成测试-->产品验收
```

阶段产出：
- 测试：测试报告
- 开发：版本(CI自动生成)
- 运维：验收环境

参考资料：
- [版本规范]({{< relref "docs/dev-guide/version.md" >}})

# 发布阶段

阶段产出：
- 测试：版本报告
- 运维：正式环境
- 开发：更新申请

# 运营阶段

阶段产出：
- 运维：运维报告
