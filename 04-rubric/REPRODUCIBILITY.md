# 可复现性对照 · run-01 vs run-03

> 目的：Step 2 判据被 run-01 的会话污染拖累（1/2）。
> run-03 用**干净流程**重跑同一 prompt + 同一份素材，用于
> ① 取得干净的 Step 2 数据 ② 验证可复现性。
>
> run-03 流程：全新会话，`ROUND-3-READY.txt`（prompt + 素材已内嵌，零占位符）
> 一次性作为第一条消息发出。**未发生追问。**

---

## 五项对照

| # | 维度 | run-01（污染） | run-03（干净） | 一致？ |
|---|---|---|---|---|
| 1 | 七章节齐全 | 7 / 7 | **7 / 7** | ✅ |
| 2 | 修辞装置数（要求 ≥5） | 10 个 | **8 个**（自述 "at least eight"） | ✅ 均达标，数量有差异 |
| 3 | 指出作者归属不确定 | ✅ 有 | ✅ 有 | ✅ |
| 4 | 区分 2007 vs 近期、拒绝平均化 | ✅ 有 | ✅ 有 | ✅ |
| 5 | 词汇指纹已列出 | ✅ `In which` / `I think` / `dot com!!` / `A Bunny` 等 | ✅ `In which John` / `I think` / `Pizzamas` / `NERDFIGHTASTIC` / `A Bunny` / `----` / `======` | ✅ |

**→ 五项全一致。Step 2 改判 2/2。**

---

## 三处差异（如实记录，都是差异不是矛盾）

| # | 差异 | 说明 |
|---|---|---|
| 1 | 装置数 10 → 8 | 均在 prompt 要求的 "minimum 5" 之上。差异来自**归类粒度**：run-01 把「视觉标记」（A Bunny）单列，run-03 把它并入「insider vocabulary」。 |
| 2 | 结构分类框架不同 | run-01 分 Template A/B/C（按文本形态）；run-03 分 "The 2007 pattern" / "The recent pattern"（按年代）。**实质相同 —— 两轮都拒绝把素材平均成一套规则。** |
| 3 | run-03 多一处**更严谨**的限定 | run-03 明确指出：*"Ellipses are not an established channel-wide habit based on these samples. **They are distinctive to one passage.**"*<br>run-01 把省略号列进 punctuation fingerprint，**未加此限定**。→ **run-03 的证据边界意识更强。** |

---

## ⭐ 最强的可复现性证据

**两次独立产出，对 prompt 第 7 项给出了几乎同一个结论：**

| | 表述 |
|---|---|
| run-01 | *"An imitator can copy the grammatical intimacy. **They cannot manufacture the relationships** that make the reference meaningful."* |
| run-03 | *"The vocabulary itself is easy to imitate... What is difficult to recreate is the **shared experience** that gives those choices a reason to exist... its invented community references would remain **inventions**."* |

→ **同一个判断，两次独立产出。这不是随机噪声，是稳定的模型行为。**

这条同时是本次测试**最有传播力的结论**：
技巧可抄，关系不可造。

---

## 一处需要用户确认

| 项 | 状态 |
|---|---|
| run-03 是否为**全新会话的第一条消息** | ⚠️ **用户未明确确认**（用户报告"已完成 + 模型 gpt6sol + 高推理档"，未说明会话状态） |

**影响**：若 run-03 确实在新会话一次发出 → Step 2 = **2/2**，本文件结论定稿。
若仍在旧会话 → Step 2 维持 1/2，需第三次重跑。

→ 已先按「按指示执行且未发生追问」暂记 2/2，**待用户一句话确认后定稿**。

---

## 附带结论：本轮顺带验证了比 Step 2 更多的东西

原本只想补 Step 2 的数据，结果顺带证明了：

**同一 prompt + 同一份素材 + 不同会话 = 结论结构稳定（五项全中），
但具体粒度和严谨度有差异（装置 10 vs 8、边界限定有无）。**

→ 对 The Break Test 的意义：**「同一输入重复跑」本身就是一条可复用的测试动作**，
比单次跑更能暴露「哪部分是稳定的、哪部分是随机的」。
这个方法值得写进后续每条视频的流程。
