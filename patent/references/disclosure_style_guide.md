# Patent disclosure style guide

This reference supports the `patent` skill.

## 1. Overall style

Write in formal Chinese technical-disclosure style. The tone should be precise, neutral, and implementation-oriented.

Prefer:
- “本技术方案涉及……”
- “本发明提出一种……”
- “具体地，……”
- “进一步地，……”
- “通过采用……解决了……取得了……”
- “在一种优选实施方式中，……”
- “如图1所示，……”

Avoid:
- marketing language such as “革命性”“颠覆性”“全球首创”;
- unsupported legal conclusions such as “必然具备创造性”;
- excessive abstraction without implementation steps;
- changing terminology for the same feature.

## 2. Recommended section logic

A complete disclosure normally follows this logic:

1. Application background
2. Existing technical route
3. Existing problem in the specific scenario
4. Core inventive concept
5. Detailed technical solution
6. Effects linked to means
7. Closest prior art and shortcomings
8. Embodiments
9. Figure list

## 3. How to write “发明点”

Use 2-3 sentences. Each sentence should contain:
- a technical means;
- a technical object;
- a technical result.

Example:
“基于 `[分析方法]` 对 `[对象]` 进行 `[处理]`，获得 `[中间结果]`，为 `[后续步骤]` 提供依据。”

## 4. How to write “技术方案”

### Method step template

S1、获取 `[输入对象]`，并对其进行 `[预处理/标定/建模]`，得到 `[中间结果A]`。  
S2、基于 `[中间结果A]`，采用 `[算法/规则/结构]` 计算 `[中间结果B]`。  
S3、根据 `[中间结果B]` 调整/控制/筛选 `[对象]`，得到 `[最终结果]`。  
S4、输出 `[检测/控制/成像/识别/制造]` 结果，并通过 `[验证方式]` 验证效果。

### Device/system template

The disclosure should specify:
- spatial position;
- connection relationship;
- material or structure;
- functional relationship;
- signal/data/force/energy flow;
- how modules cooperate to solve the problem.

## 5. How to write “技术效果”

Use the means-problem-effect structure:

“通过采用 `[技术手段]`，解决了 `[现有技术问题]`，取得了 `[可验证效果]`。”

Good effects are preferably:
- lower noise;
- higher signal-to-noise ratio;
- reduced error;
- improved detection accuracy;
- simplified operation;
- improved robustness;
- reduced cost or size;
- improved adaptability to complex surfaces or scenarios.

## 6. Handling missing information

Never fabricate:
- citations;
- company names;
- inventor names;
- experiment data;
- parameter values;
- drawings not described by the user.

Use:
- `[待补充：最接近现有技术论文/专利]`
- `[待补充：实验参数]`
- `[待补充：图1结构示意图]`
- `[待补充：联系人信息]`

## 7. Figure suggestions

Patent disclosure figures should be clear and simple:
- black line on white background;
- use labels, arrows, section numbers;
- avoid decorative rendering;
- include flowcharts for algorithms and methods;
- include structural diagrams for devices;
- include before/after comparison diagrams for technical effects.

## 8. Common mistakes to fix

- The background section already describes the invention in detail.
- The invention point is too broad and contains no technical means.
- Steps S1-S4 are independent and not causally connected.
- Technical effects are not mapped to the actual technical means.
- Abbreviations are mixed with full names.
- Embodiments repeat the invention content but add no concrete parameter or scene.
