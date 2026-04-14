---
name: prd-generator
description: 基于页面实现、spec.md文档和功能范围，匹配指定模板类型生成面向研发测试的结构化PRD，确保与技术约定一致并核对一致性。Invoke when user asks to generate PRD.
---

# PRD Generator Skill

## Overview
基于页面实现代码、spec.md规格文档及用户指定的功能范围，智能识别页面类型并匹配对应模板，生成面向研发和测试人员的结构化产品需求文档（PRD）。

## When to Use
- 用户明确要求生成PRD文档时
- 用户需要将已实现的页面转化为PRD文档时
- 用户需要根据spec.md生成正式PRD时

## Template Types

### 1. 数据看板类 (data-prd-template.md)
**适用场景**：
- 数据统计看板
- 报表分析页面
- 指标监控页面

**重点内容**：
- 指标定义和数据口径
- 数据来源说明
- 筛选条件
- 图表说明
- 交互规则

### 2. 后台列表类 (backend-list-prd-template.md)
**适用场景**：
- 数据列表管理页面
- 查询列表页面
- 台账管理页面

**重点内容**：
- 筛选条件
- 列表字段定义
- 排序规则
- 分页规则
- 批量操作
- 行操作

### 3. 后台表单编辑类 (backend-form-edit-prd-template.md)
**适用场景**：
- 新增/编辑表单页面
- 配置管理页面
- 数据录入页面

**重点内容**：
- 字段定义
- 字段校验规则（必填、长度、格式）
- 默认值
- 字段联动逻辑
- 提交规则

### 4. 后台表单预览类 (backend-form-preview-prd-template.md)
**适用场景**：
- 详情查看页面
- 预览页面
- 只读页面

**重点内容**：
- 字段展示规则
- 数据展示格式
- 操作按钮

### 5. 用户前台类 (user-frontend-prd-template.md)
**适用场景**：
- C端用户页面
- 营销活动页面
- 产品展示页面

**重点内容**：
- 用户交互场景
- 功能触发条件
- 操作反馈
- 展示规范

## Workflow

### Step 1: 页面分析
1. 读取目标页面的 `index.tsx`（或主要实现文件）
2. 读取 `spec.md` 规格文档（如果存在）
3. 读取 `content.md` 或其他相关文档
4. 查看 `screenshot.png` 了解页面视觉

### Step 2: 类型识别
基于页面内容自动识别类型：
- 包含大量图表、指标 → 数据看板类
- 包含列表、筛选、分页 → 后台列表类
- 包含表单输入、提交 → 后台表单编辑类
- 只有展示、无输入 → 后台表单预览类
- C端用户界面 → 用户前台类

### Step 3: 需求确认
向用户确认：
1. PRD的页面类型（如未自动识别）
2. 是否有指定的功能范围
3. 特殊要求或关注点

### Step 4: PRD生成
1. 应用对应模板
2. 从页面实现和spec.md中提取信息
3. 填充模板内容
4. 保存到 `<project-dir>/src/prototypes/<page-name>/prd.md`

### Step 5: 一致性核对
核对以下维度：
- ✅ 功能点与页面实现一致
- ✅ 技术约定与spec.md一致  
- ✅ 范围与用户要求一致
- ✅ 无遗漏核心内容

如有不一致，返回Step 4重新生成。

## Rules
1. **路径规范**：PRD必须保存到 `src/prototypes/<page-name>/prd.md`
2. **命名规范**：文件名必须为 `prd.md`（小写）
3. **术语规范**：使用研发/测试通用术语
4. **范围约束**：用户指定范围时，不超出范围
5. **必须核对**：生成后必须进行一致性核对

## Example Usage

```
用户：帮我生成 data-search 页面的PRD
→ 执行：
  1. 分析 index.tsx 和 spec.md
  2. 识别为数据看板类
  3. 应用 data-prd-template.md
  4. 生成 src/prototypes/data-search/prd.md
  5. 核对一致性
```
