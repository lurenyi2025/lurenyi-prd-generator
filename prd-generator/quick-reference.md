# PRD Generator 快速参考指南

## 🚀 快速开始

### 一句话命令

```
帮我生成 [页面路径] 的PRD
```

### 示例

```
帮我生成 data-search 页面的PRD
帮我生成 src/prototypes/xyop-ciku-list 的PRD
```

***

## 📋 页面类型速查表

| 图标  | 类型      | 适用场景              | 模板                                   |
| --- | ------- | ----------------- | ------------------------------------ |
| 📊  | 数据看板类   | 统计看板、报表分析、指标监控    | data-prd-template.md                 |
| 📋  | 后台列表类   | 数据列表、查询列表、台账管理    | backend-list-prd-template.md         |
| ✏️  | 后台表单编辑类 | 新增/编辑表单、配置管理、数据录入 | backend-form-edit-prd-template.md    |
| 👁️ | 后台表单预览类 | 详情查看、预览页面、只读页面    | backend-form-preview-prd-template.md |
| 🎨  | 用户前台类   | C端页面、营销活动、产品展示    | user-frontend-prd-template.md        |

***

## 🎯 指定页面类型

如果需要强制使用某种类型，可以这样说：

```
帮我生成 [页面路径] 的PRD，使用数据看板类模板
帮我生成 [页面路径] 的PRD，使用后台列表类模板
```

***

## 🔍 指定功能范围

如果只需要生成部分功能的PRD：

```
帮我生成 [页面路径] 的PRD，只包含筛选和列表部分
帮我生成 [页面路径] 的PRD，重点关注表单编辑功能
```

***

## 📁 文件结构

```
skills/prd-generator/
├── SKILL.md                    # 主技能文档
├── workflow.md                 # 详细工作流程
├── quick-reference.md          # 本文件 - 快速参考
└── template/
    ├── data-prd-template.md              # 数据看板模板
    ├── backend-list-prd-template.md      # 后台列表模板
    ├── backend-form-edit-prd-template.md # 表单编辑模板
    ├── backend-form-preview-prd-template.md # 表单预览模板
    └── user-frontend-prd-template.md     # 用户前台模板
```

***

## ✅ 输出检查清单

生成PRD后，请确认：

- [ ] 文件保存在正确位置：`src/prototypes/<page-name>/prd.md`
- [ ] 文件名正确：`prd.md`（小写）
- [ ] 内容与页面实现一致
- [ ] 内容与spec.md一致（如果有）
- [ ] 没有遗漏核心功能
- [ ] 使用了研发/测试通用术语
- [ ] 结构清晰、层次分明

***

## 💡 常用提示词

### 基础使用

```
帮我生成 data-search 页面的PRD
```

### 指定类型

```
帮我生成 data-search 页面的PRD，使用数据看板类模板
```

### 指定范围

```
帮我生成 data-search 页面的PRD，重点关注找供应商看板
```

### 详细要求

```
帮我生成 data-search 页面的PRD，需要详细描述数据口径和指标定义
```

***

## 🆘 常见问题

### Q: 生成的PRD保存在哪里？

A: 保存在 `src/prototypes/<page-name>/prd.md`

### Q: 可以修改已生成的PRD吗？

A: 可以，直接告诉需要修改的内容即可。如果修改了页面实现，建议重新生成PRD。

### Q: 页面同时有列表和表单怎么办？

A: 选择主要功能类型，其他功能在对应模块详细描述

### Q: spec.md不存在怎么办？

A: 只基于页面实现生成PRD，不依赖spec.md

***

## 📞 获取帮助

如果遇到问题，可以这样问：

```
这个页面应该用哪种模板？
帮我看看这个页面属于什么类型？
生成PRD时需要注意什么？
```

