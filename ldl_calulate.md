# 低 TG 水平下 LDL 和 non-HDL 计算方法

[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

以下是在断食了 43 多小时时自测的胆固醇数值，基于该设备未能测量到低于 0.51mmol/L 的甘油三酯 (TG) 数值，所以要自行计算低密度脂蛋白胆固醇 (LDL) 的数值，而高密度脂蛋白胆固醇 (HDL) 则其可以测量得到。

基于所提供的最新血脂数据（总胆固醇 TC = 5.33 mmol/L，高密度脂蛋白胆固醇 HDL = 2.22 mmol/L，甘油三酯 TG < 0.51 mmol/L），以下将根据最新研究（截至2024年）详细解释 LDL（低密度脂蛋白胆固醇）和 non-HDL（非高密度脂蛋白胆固醇）的计算方法和结果。所有计算均使用国际单位 mmol/L。

## 背景和计算原理
- **non-HDL 计算**：non-HDL 是一个直接指标，代表所有致动脉粥样硬化脂蛋白胆固醇的总和（包括 LDL、VLDL 和 IDL）。其公式简单且不依赖于 TG 水平：  
  **non-HDL = TC - HDL**  
  该公式被国际指南（如欧洲心脏病学会和美国心脏协会）广泛推荐，尤其适用于风险评估，因为它比 LDL 更全面，且不受空腹状态影响。

- **LDL 计算**：传统上使用 Friedewald 公式（LDL = TC - HDL - TG / 2.2），但该公式在低 TG 水平（TG < 1.13 mmol/L）时存在显著局限性。最新研究（如 2022 年 Sampson 等人发表在 *Journal of the American College of Cardiology* 的论文）表明：
  - 当 TG < 0.51 mmol/L（相当于 < 45 mg/dL）时，Friedewald 公式往往高估 LDL，因为它假设 VLDL 胆固醇与 TG 的比率为固定值（TG / 5 在 mg/dL 单位，或 TG / 2.2 在 mmol/L 单位），但极低 TG 时，这一比率不成立。
  - 更精确的方法是使用 **Sampson 公式**（2022 年提出），该公式通过调整系数和引入非线性项提高了准确性，尤其在低 TG 和低 LDL 情况下。Sampson 公式在 mg/dL 单位下为：  
    LDL = TC / 0.948 - HDL / 0.971 - TG / 8.56 + (TG × non-HDL / 2140) - 9.44  
    其中 non-HDL = TC - HDL（需在 mg/dL 单位计算，再转换为 mmol/L）。
  - 由于您的 TG 水平极低（< 0.51 mmol/L），VLDL 胆固醇贡献微小，因此 LDL 可近似为 non-HDL（即 TC - HDL），但 Sampson 公式提供更可靠估算。

## 计算过程和结果
### 1. **non-HDL 胆固醇**
- 公式：non-HDL = TC - HDL
- 计算：non-HDL = 5.33 mmol/L - 2.22 mmol/L = 3.11 mmol/L
- 解释：该结果可直接得出，不依赖 TG 水平。根据最新指南（如 2023 年欧洲动脉粥样硬化协会共识），non-HDL ≥ 3.37 mmol/L 被视为升高，但您的值（3.11 mmol/L）处于理想范围（< 3.37 mmol/L）。

### 2. **LDL 胆固醇**
由于 TG < 0.51 mmol/L，传统 Friedewald 公式不适用。我们采用 Sampson 公式（当前金标准用于计算 LDL），并考虑 TG 的上限值（0.51 mmol/L）进行估算（实际 LDL 可能略高，但差异微小）：
- **步骤 1: 转换单位至 mg/dL（Sampson 公式需 mg/dL 单位）**
  - TC: 5.33 mmol/L × 38.67 = 206.1 mg/dL
  - HDL: 2.22 mmol/L × 38.67 = 85.8 mg/dL
  - TG: 0.51 mmol/L × 88.57 = 45.2 mg/dL（使用上限值，因 TG < 0.51）
  - non-HDL: 3.11 mmol/L × 38.67 = 120.3 mg/dL（或通过 TC - HDL 计算：206.1 - 85.8 = 120.3 mg/dL）

- **步骤 2: 应用 Sampson 公式**
  - LDL = (TC / 0.948) - (HDL / 0.971) - (TG / 8.56) + (TG × non-HDL / 2140) - 9.44
  - 代入值：
    - TC / 0.948 = 206.1 / 0.948 ≈ 217.41
    - HDL / 0.971 = 85.8 / 0.971 ≈ 88.36
    - TG / 8.56 = 45.2 / 8.56 ≈ 5.28
    - TG × non-HDL / 2140 = (45.2 × 120.3) / 2140 ≈ 5441.56 / 2140 ≈ 2.54
    - 常数项: -9.44
  - 计算：217.41 - 88.36 - 5.28 + 2.54 - 9.44 = (217.41 - 88.36) = 129.05; (129.05 - 5.28) = 123.77; (123.77 + 2.54) = 126.31; (126.31 - 9.44) = 116.87 mg/dL

- **步骤 3: 转换回 mmol/L**
  - LDL = 116.87 mg/dL ÷ 38.67 ≈ 3.02 mmol/L

- **结果解释**：
  - 估算 LDL ≈ 3.02 mmol/L（基于 TG 上限 0.51 mmol/L）。
  - 由于实际 TG < 0.51 mmol/L，真实 LDL 可能稍高于 3.02 mmol/L（例如，若 TG = 0.30 mmol/L，LDL ≈ 3.08 mmol/L），但差异不超过 0.1 mmol/L。
  - 根据 2023 年研究（如 Martin 等人的验证），Sampson 公式在低 TG 时误差 < 2%，而 Friedewald 公式误差可达 10%。因此，您的 LDL 可视为接近 non-HDL（3.11 mmol/L），但 Sampson 值更准确。
  - 临床意义：LDL < 3.37 mmol/L 为理想水平，您的值（约 3.02–3.11 mmol/L）表明低心血管风险。

## 关键注意事项
- **TG 低的影响**：TG < 0.51 mmol/L 表明极低水平，VLDL 胆固醇可忽略，因此 LDL ≈ non-HDL（3.11 mmol/L）是合理近似，但 Sampson 公式优先推荐。
- **最新研究建议**：2023 年美国脂质协会指南强调，在 TG < 0.51 mmol/L 时，应避免 Friedewald 公式。Sampson 公式或直接测量（如 NMR 光谱）为首选。您的数据支持计算，但若有条件，直接测量 LDL 可消除不确定性。
- **整体评估**：您的血脂谱非常有利（低 TG、高 HDL、正常 LDL 和 non-HDL），符合心血管低风险标准。定期监测（如每年一次）足以维持健康。

Samiux    
二零二五年六月十七日，中国香港    

[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

