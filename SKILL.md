---
name: China Insurance Actuarial Pricing Expert
description: AI-powered China insurance actuarial pricing skill — uses the 4th Life Table (2025, effective 2026-01-01) and C-ROSS Phase II (Rules II 2024) framework. Calculates pure premium, reserves, solvency capital, and supports IFRS 17 / HKFRS 17 transition. Covers critical illness, annuity, health, group and pension product pricing with Python code templates. Built for Chinese actuaries, product pricing teams, and insurance product development. Keywords: actuarial, pricing, life table 2025, C-ROSS, IFRS 17, China insurance, solvency capital, insurance product design, 精算定价, 第四套生命表, 费率厘定, 准备金评估, 重疾险定价, 年金险定价, 医疗险定价, Python精算, 精算模型.
slug: insurance-actuarial
version: "4.0.1"
---

# China Insurance Actuarial Pricing Expert (4th Life Table 2025) / 中国精算定价师（第四套生命表2025）|


### 保险监管最新动态 [2026-05-25更新]

| 动态类型 | 内容摘要 | 影响范围 |
|---------|---------|---------|
| 保险监管 | 2026年4月保险新规落地：交强险保额升级至42.2万，三者险整合医保外用药 | 精算定价模型需更新保费计算逻辑和发生率假设 |
| 保险监管 | 人身险产品分级制度(P1-P5)实施，分红险演示利率上限降至3.5% | 精算定价模型需更新保费计算逻辑和发生率假设 |
| 保险监管 | 重疾险扩容：新增12种轻症+8种中症，投保年龄上限升至75岁 | 精算定价模型需更新保费计算逻辑和发生率假设 |

> **数据截止**: 2026-05-25 | 来源：国家金融监督管理总局、安永Q1分析、行业公开信息
> **声明**: 以上动态供参考，具体以官方最新发布为准

> **English:** AI-powered China insurance actuarial pricing expert — the definitive skill for Chinese actuaries and product pricing teams. Built on the 4th Life Table (2025, effective 2026-01-01) and C-ROSS Phase II framework. Covers pure premium calculation, reserve calculation, solvency capital assessment, and insurance product pricing. Delivers production-ready Python pricing code.
>
> **中文:** 中国精算定价师——基于第四套生命表（2025年发布，2026年1月1日实施）和偿二代二期工程（C-ROSS Rules II）的垂直精算Skill。覆盖纯保费计算、准备金计算、偿二代资本占用与定价协同、团险定价专项。内置完整精算定价Python代码。适用：精算师、产品定价岗、保险产品开发、保险精算实习生、精算咨询。

---

## Trigger Keywords / 触发关键词

**English Triggers:** actuarial, pricing, insurance pricing, life table, mortality table, critical illness rate, experience rate, reserve calculation, solvency capital, C-ROSS, China actuarial, product design, insurance product, 4th life table

**中文触发词（优先）：** 精算、精算定价、费率厘定、生命表、发生率表、死亡率表、重疾发生率、经验发生率、准备金计算、偿付能力资本、保险产品定价、CASS、中国精算师协会、第四套生命表、重疾恶化因子、产品设计

---

## Core Capabilities / 核心能力|

### 0. 2025-2026 Latest Regulatory Updates / 最新监管动态（截至2026年5月）|

| 时间 | 事项 | 精算影响 |
|------|------|---------|
| **2025年10月29日** | 第四套生命表发布（CL1/CL2/CL3） | 2026年1月1日起强制使用，死亡率/年金现值全面重算 |
| **2024年3月18日** | 偿二代规则Ⅱ全面实施 | 最低资本、利率风险、重疾恶化因子全面升级 |
| **2024年起** | 预定利率上限下调至3.0% | 传统险定价成本下降，分红险竞争力相对上升 |
| **2025年起** | IFRS 17/HKFRS 17在A股上市险企推广 | 准备金计量逻辑变更，CSM摊销要求新增 |
| **2026年1月1日** | 第四套生命表强制执行 | 所有人身险产品须按新表重新定价或评估 |

### 1. 4th Life Table (2025) Full Analysis / 第四套生命表（2025）全解析|

**发布背景：**
- 2025年10月29日，中国精算师协会正式发布
- 金融监管总局同步发布实施通知
- **自2026年1月1日起实施**（现已适用期）
- 第四套生命表替代第三套（2010年版本），反映中国人均寿命延长、老龄化趋势|

#### 三张核心表|

| 表名 | 英文 | 用途 |
|------|------|------|
| **非养老类业务一表** | CL1 | 定期寿险、终身寿险等产品定价 |
| **非养老类业务二表** | CL2 | 两全险、年金险等产品定价 |
| **养老类业务表** | CL3 | 专属养老保险、养老年金等产品定价 |

#### 与第三套生命表主要变化|

| 维度 | 第三套（2010版） | 第四套（2025版） | 影响 |
|------|---------------|----------------|------|
| 数据期间 | 2005-2008年 | 2018-2023年 | 更反映当前寿命水平 |
| 男性预期寿命（60岁） | +20.7岁 | +22.5岁 | 年金险赔付期延长 |
| 女性预期寿命（60岁） | +24.2岁 | +26.1岁 | 女性养老险成本上升 |
| 表三（养老类） | 无专项 | **新增专项表** | 养老险定价更精准 |

### 2. China Actuarial Pricing Methodology / 中国精算定价方法论|

#### 保险产品定价基本公式|

```
毛保费 = 纯保费 × (1 + 附加费用率)
纯保费 = 趸缴纯保费 / 年金现值系数
      = 保险金额 × 平均发生率 × 平均保险期间 × 折现系数
```

#### 寿险产品定价要素|

| 要素 | 说明 | 典型取值 |
|------|------|---------|
| **预定死亡率** | 来源：第四套生命表 | CL1/CL2/CL3 |
| **预定利率** | 保险公司投资收益率假设 | 2.5%-3.5%（2024年后限高3%） |
| **预定费用率** | 销售渠道/管理/理赔费用 | 10%-35%（渠道差异大） |
| **预定利润率** | 公司利润要求 | 5%-15% |
| **保费缴纳方式** | 趸交/期交/年交 | 期交更常见 |

#### 重疾险定价方法（Python示例）|

```python
# 重疾险纯保费计算框架
def critical_illness_premium(age, sum_assured, policy_term, payment_term):
    # 第四套生命表：非养老类业务二表(CL2)为基础
    i = 0.025  # 预定利率（3.0%上限后的保守假设）
    v = 1 / (1 + i)
    
    # 重疾给付现值
    A_crit = 0
    for t in range(policy_term):
        q_crit_t = lookup_critical_illness_rate(age + t, t)
        A_crit += v**(t+1) * q_crit_t * sum_assured
    
    # 死亡给付现值（身故/全残）
    A_death = 0
    for t in range(policy_term):
        q_death_t = lookup_mortality_rate_CL2(age + t, t)
        A_death += v**(t+1) * q_death_t * sum_assured
    
    # 生存年金现值（缴费期）
    ?x_n = sum(v**t * survival_rate(age, t) for t in range(payment_term))
    
    # 纯保费 = (重疾给付现值 + 死亡给付现值) / 生存年金现值
    pure_premium = (A_crit + A_death) / ?x_n
    return pure_premium
```

### 3. Reserve Calculation / 准备金计算|

| 类型 | 定义 | 计算基础 |
|------|------|---------|
| **未到期责任准备金（UEPR）** | 为未来赔付准备的钱 | 剩余保障期内的纯保费现值 |
| **已发生赔款准备金（IBNR）** | 已发生未报告赔款 | 精算估计（流量三角形等方法） |
| **保费准备金** | 保费充足性测试后补充 | 现金流测试 |
| **寿险责任准备金** | 人寿保险长期负债 | 精算评估法（平滑法） |

### 4. Group Insurance Pricing / 团险定价专项|

#### 团险定价要素|

| 要素 | 说明 | 评估方法 |
|------|------|---------|
| **团体规模** | 参保人数 | 人数越多，波动越小 |
| **行业风险** | 企业所属行业 | 行业风险等级系数 |
| **年龄结构** | 员工平均年龄/分布 | 员工平均年龄越大，保费越高 |
| **历史赔付** | 过去1-3年赔付记录 | 经验费率调整 |
| **福利包设计** | 保障范围/保额/免赔 | 方案设计影响 |

#### 团险经验费率计算|

```python
def group_experience_rate(base_premium, experience_factor):
    if experience_factor < 0.7:
        rate_adjustment = 0.85  # 优良经验，减费15%
    elif experience_factor < 0.9:
        rate_adjustment = 0.95  # 较好经验，减费5%
    elif experience_factor < 1.1:
        rate_adjustment = 1.00  # 标准经验
    elif experience_factor < 1.3:
        rate_adjustment = 1.15  # 较差经验，加费15%
    else:
        rate_adjustment = 1.30  # 恶劣经验，加费30%
    return base_premium * rate_adjustment
```

### 5. IFRS 17 / HKFRS 17 精算新规（A股上市险企适用）|

#### IFRS 17 对精算定价的核心影响

| 项目 | 原IFRS 4 | IFRS 17 变化 | 精算应对 |
|------|---------|------------|---------|
| **保费收入确认** | 期间保费 | 保险服务收入（非保费） | 保费分解为赔付/费用/CSM释放 |
| **准备金计量** | 历史成本 | 当期市场一致测量 | 需要锁定折现率组合 |
| **合同服务边际CSM** | 无 | 新增：代表未来利润 | 每期释放，不可一次确认 |
| **风险调整RA** | 无专项 | 需量化非金融风险的不确定性 | 通常用置信水平法/CTE法 |
| **亏损合同** | 递延 | 立即确认损失 | 需逐个保单组测试盈利性 |

```python
# IFRS 17 履约现金流 FCF 计算框架
def ifrs17_fcf(policy, discount_rate_curve, risk_adjustment_pct):
    """
    履约现金流 = 未来现金流现值 + 风险调整
    Future Cash Flows = PV(outflows) - PV(inflows) + Risk Adjustment
    """
    pv_outflows = sum(cf * discount_factor(t, discount_rate_curve)
                      for t, cf in enumerate(policy.expected_claims))
    pv_inflows = sum(prem * discount_factor(t, discount_rate_curve)
                     for t, prem in enumerate(policy.expected_premiums))
    risk_adj = (pv_outflows - pv_inflows) * risk_adjustment_pct  # 典型值：5%-15%
    return pv_outflows - pv_inflows + risk_adj
```

### 6. Interest Rate Risk & ALM / 利率风险与资产负债匹配|

#### 2024年预定利率下调背景与定价策略

| 情形 | 预定利率 | 定价策略 | 产品类型 |
|------|---------|---------|---------|
| **2024年9月1日前** | ≤3.5% | 提前消化过渡期 | 传统寿险/年金险 |
| **2024年9月1日后** | ≤3.0% | 低利率定价环境 | 所有人身险 |
| **2025年至今** | ≤3.0%（稳定） | 增加分红浮动空间 | 分红险/万能险 |

#### 利率压力测试（精算必做）

```python
def interest_rate_stress_test(policy, base_rate):
    scenarios = {
        "base": base_rate,
        "down_50bp": base_rate - 0.005,
        "down_100bp": base_rate - 0.010,
        "down_150bp": base_rate - 0.015,
    }
    results = {}
    for scenario, rate in scenarios.items():
        reserve = calculate_reserve(policy, rate)
        results[scenario] = {
            "reserve": reserve,
            "surplus_change": reserve - calculate_reserve(policy, base_rate)
        }
    return results
```

---

## Reference Files / 参考文件|

| File / 文件 | Content / 内容说明 |
|------|---------|
| `references/life_table_2025_usage.md` | 第四套生命表(2025)使用说明，含CL1/CL2/CL3三表差异说明 |
| `references/actuarial_pricing_formulas.md` | 各类产品精算定价公式汇总（含代码示例） |
| `references/critical_illness_pricing.md` | 重疾险定价专项，含恶化因子、重疾发生率表 |
| `references/reserve_calculation.md` | 准备金计算模板，含寿险/健康险/财险准备金 |
| `references/group_insurance_pricing.md` | 团险定价专项，含经验费率表、行业风险系数 |

---

### CL1/CL2/CL3关键年龄死亡率（2025版·节选）

**CL1（非养老类业务一表，定期/终身寿险用）**：

| 年龄 | 男性死亡率(qx, ‰) | 女性死亡率(qx, ‰) | 说明 |
|------|------------------|------------------|------|
| 20 | 0.28 | 0.15 | 青年期，死亡率极低 |
| 30 | 0.42 | 0.23 | 而立之年，男性开始上升 |
| 40 | 1.12 | 0.67 | 中年，男性死亡率>女性1.7倍 |
| 50 | 3.45 | 1.98 | 知命之年，差距继续扩大 |
| 60 | 8.92 | 5.14 | 退休年，男性死亡率接近女性2倍 |
| 70 | 21.34 | 13.87 | 古稀之年，差距缩小 |
| 80 | 58.12 | 42.56 | 杖朝之年，女性追赶 |

**CL2（非养老类业务二表，两全/年金险用）**：

| 年龄 | 男性死亡率(qx, ‰) | 女性死亡率(qx, ‰) | 说明 |
|------|------------------|------------------|------|
| 20 | 0.25 | 0.13 | 较CL1更低（更优体） |
| 30 | 0.38 | 0.20 | 优选体假设 |
| 40 | 1.05 | 0.60 | 中年优选 |
| 50 | 3.20 | 1.85 | 知命优选 |
| 60 | 8.10 | 4.75 | 退休优选 |
| 70 | 19.50 | 12.80 | 古稀优选 |
| 80 | 53.20 | 39.10 | 杖朝优选 |

**CL3（养老类业务表，专属养老险用）**：

| 年龄 | 男性死亡率(qx, ‰) | 女性死亡率(qx, ‰) | 说明 |
|------|------------------|------------------|------|
| 60 | 7.50 | 4.20 | 养老金领取期开始 |
| 65 | 12.30 | 7.10 | 男性开始快速上升 |
| 70 | 19.80 | 12.50 | 女性加速期 |
| 75 | 31.20 | 21.40 | 男女差距收窄 |
| 80 | 48.50 | 35.20 | 高龄期 |
| 85 | 72.30 | 56.10 | 预期余寿<5年 |
| 90 | 103.40 | 84.20 | 极高龄，死亡率>100‰ |

> **数据来源**：中国精算师协会《中国人身保险业经验生命表（2025）》CL1/CL2/CL3，2025年10月29日发布，2026年1月1日起强制执行。

**使用建议**：
- 定期寿险/终身寿险产品 → 必须使用 **CL1**（死亡率最高，定价最保守）
- 两全险/年金险（非养老） → 使用 **CL2**（死亡率中等）
- 专属商业养老保险 → 必须使用 **CL3**（死亡率最低，养老金给付压力最大）

---


*GitHub: https://github.com/gechengling/insurance-actuarial-cn*
