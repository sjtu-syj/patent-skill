---
name: patent
description: Use this skill to draft, expand, revise, or standardize Chinese patent technical disclosure documents (技术交底书/专利交底书) from invention highlights, implementation details, experiments, algorithms, structures, drawings, or technical notes. Trigger on requests mentioning 专利交底书, 技术交底书, 发明点, 技术方案, 技术效果, 实施例, 图纸说明, 背景技术, 最接近现有技术. Do not use for legal validity opinions, freedom-to-operate opinions, or final attorney filing advice.
---

# Patent technical disclosure drafting skill

## Purpose

Create a structured Chinese patent technical disclosure document from the user's technical notes. The default output is a **技术交底书**, not a final attorney-filed patent application.

Use this skill when the user wants to:
- write a new technical disclosure from technical highlights and implementation details;
- expand rough invention notes into a complete disclosure;
- revise an existing disclosure for structure, terminology consistency, completeness, and patent-readiness;
- generate figure lists, embodiment sections, technical effects, or background/closest-prior-art sections for a disclosure.

## Core principles

1. **Do not invent key technical facts.** If necessary facts are missing, continue drafting with clear placeholders like `[待补充：具体参数]` instead of fabricating numbers, experiments, prior art, company names, inventors, or citations.
2. **Keep terminology consistent.** Choose one name for each concept and use it throughout. If the user provides both a full name and abbreviation, introduce the abbreviation once, then use it consistently.
3. **Make steps causally linked.** Outputs/products from earlier steps must be used by later steps. Avoid isolated steps that do not contribute to the final technical effect.
4. **Tie every effect to a means.** Describe technical effects using the pattern: “通过采用……的方法/结构/步骤，解决了……的问题，取得了……的效果。”
5. **Preserve technical detail.** Keep equations, variables, dimensions, material names, device parameters, signal-processing steps, model structures, and experiment conditions when provided. Define variables immediately after equations.
6. **Stay neutral on legal conclusions.** Use phrases like “有利于”“能够”“可实现”“可降低”，unless the user supplied verified data. Do not guarantee authorization, novelty, inventiveness, or non-infringement.
7. **Prefer black-line figure suggestions.** For disclosure drawings, recommend black lines on white background, with clear labels, arrows, flowcharts, structural diagrams, test result diagrams, and parameter annotations.

## Default workflow

When drafting from scratch:

1. Extract from the user's notes:
   - invention name;
   - technical field;
   - application scenario;
   - pain points in existing technology;
   - core inventive concept;
   - key structures/modules/steps;
   - input/output data;
   - parameters and equations;
   - embodiments and validation data;
   - figure materials and figure captions;
   - closest prior art or keywords, if available.
2. If missing information prevents meaningful drafting, ask only the minimum necessary questions. Otherwise draft with `[待补充]` placeholders.
3. Produce the disclosure in the required structure below.
4. At the end, add a short “待补充信息清单” listing only the most important missing items.

## Required output structure

Use this exact structure unless the user asks for another format.

# 文件名称：技术交底书

# 基本信息（Part A）

1、专利名称：  
`[根据技术主题生成一个准确、偏保护范围适中的名称]`

2、填写人的姓名、电话、邮箱：  
`[待补充]`

# 技术要点（Part B）

## 表述要求

- 同一概念在全文中采用统一名称表述，避免全称、简称、旧称混用。
- 在先步骤中形成的中间结果、数据、结构或模型，应被后续步骤使用。
- 技术效果应与技术手段一一对应，避免只写效果、不写实现方式。

## 1、提炼发明点

用 2-3 句话概括核心构思。优先写成以下模式：

- 第一处发明点：`[通过什么关键分析/结构/算法/控制方式]，[实现什么功能]，[为后续步骤提供什么依据]。`
- 第二处发明点：`[提出什么系统/方法/流程]，[通过什么改进]，[解决什么问题]。`
- 第三处发明点（可选）：`[验证/应用/扩展方式]，[带来什么效果]。`

## 2、具体技术方案

### 一、技术领域

写 1 段。格式：
“本技术方案涉及 `[技术领域]`，尤其涉及一种 `[专利名称核心]`，旨在 `[直接技术目的]`。”

### 二、背景技术

写 2-4 段，按照以下顺序：
1. 应用对象或产业背景；
2. 现有主流技术及其优点；
3. 现有技术在本场景下的不足；
4. 引出本发明要解决的技术问题。

Avoid overclaiming. Do not write unsupported “目前尚无任何方法” unless the user supplied evidence.

### 三、发明内容

先写总述段，然后分条描述。按技术类型选择组织方式：

#### A. 方法类发明

用 S1、S2、S3……描述。每一步写清楚：
- 输入是什么；
- 处理/计算/控制/判断怎么做；
- 输出是什么；
- 输出如何进入下一步。

Recommended form:

S1、`[获取/构建/标定/预处理]`：……  
S2、`[分析/识别/估计/分离]`：……  
S3、`[优化/控制/重构/融合]`：……  
S4、`[输出/成像/检测/验证]`：……

#### B. 装置/系统类发明

按模块描述：
- `[模块1]`：位置、组成、输入输出、功能；
- `[模块2]`：与模块1的连接关系和作用；
- `[控制/处理模块]`：执行的方法步骤；
- `[输出模块]`：输出结果和用途。

#### C. 算法/软件类发明

按数据流描述：
- 数据采集与标注；
- 先验特征或预处理；
- 网络/模型/算法结构；
- 训练或优化策略；
- 推理输出与评价指标；
- 与硬件或应用场景的配合方式。

#### D. 实验验证类内容

写明：
- 试样/对象；
- 装置/参数；
- 对比方法；
- 评价指标；
- 结果现象；
- 结果如何证明技术效果。

## 3、取得的技术效果

按“手段—问题—效果”写 2-5 条。每条尽量具体：

1. 通过采用 `[技术手段1]`，解决了 `[技术问题1]`，取得了 `[效果1]`。
2. 通过采用 `[技术手段2]`，解决了 `[技术问题2]`，取得了 `[效果2]`。
3. 通过采用 `[技术手段3]`，解决了 `[技术问题3]`，取得了 `[效果3]`。

If there are quantitative results, include them; otherwise use qualitative but restrained wording.

## 4、与本专利最接近的技术及其缺点

If the user provides prior art, summarize it and its shortcomings. If not, write placeholders instead of inventing.

Required subitems:
- 最接近的公开专利/论文/产品/方法：`[待补充]`
- 其主要技术方案：`[概括]`
- 其缺点：`[缺点1；缺点2；缺点3]`
- 同行公司名称：`[待补充]`
- 同行发明人/作者：`[待补充]`
- 本专利关键词：`[关键词1；关键词2；关键词3；关键词4]`

## 5、具体实施过程中的优选方案

Write 2-4 embodiments when possible.

### 实施例1：总体结构/总体流程

Describe the basic embodiment, including object, apparatus, parameters, and complete operation process.

### 实施例2：关键步骤或关键模块

Expand the most inventive step/module with enough technical details, equations, thresholds, variables, and decision logic.

### 实施例3：验证或对比实验

Describe comparison, expected results, and how results support the claimed effects.

### 实施例4：可选变形方案

Describe equivalent substitutions, alternative parameters, other application scenarios, or expansion forms.

# 提供图纸（Part C）

## 图纸要求

- 颜色：黑线白底图；
- 内容：流程图、原理图、结构图、测试结果图、信号处理流程图、系统框图、实验对比图等；
- 每张图应有图号、图名、关键标注、箭头方向和必要参数。

## 建议提供的图纸

图1 `[总体结构/应用场景示意图]`：……  
图2 `[方法流程图/算法流程图]`：……  
图3 `[关键模块/关键步骤原理图]`：……  
图4 `[实施例或对比实验结果图]`：……  
图5（可选）`[参数关系/数据处理/控制逻辑图]`：……

# 待补充信息清单

Only include missing facts that materially affect patent disclosure quality, such as:
- applicant/inventor/contact;
- exact apparatus structure or software architecture;
- parameters, formulas, thresholds, training data, or experimental settings;
- closest prior art documents;
- figures or screenshots to be converted into patent drawings;
- quantitative results and comparison baseline.

## Revision mode

When revising an existing disclosure:
1. Keep the user's technical meaning unchanged.
2. Improve section order and logical linkage.
3. Unify terminology.
4. Convert vague effects into means-problem-effect language.
5. Add `[待补充]` markers rather than inventing facts.
6. Return either a full revised version or a “修改建议 + 修改后文本”, depending on the user's request.

## Quality checklist before final answer

Before returning, verify:
- Part A, Part B, and Part C are present.
- The invention points are 2-3 concise paragraphs or bullets.
- Background does not disclose the invention prematurely.
- The technical solution contains concrete steps/modules.
- Earlier intermediate results are used by later steps.
- Effects correspond to the stated technical means.
- Closest prior art is not fabricated.
- Figure list matches the technical solution and embodiments.
- Missing information is clearly marked.
