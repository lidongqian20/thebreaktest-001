# Round 2 Prompt · Step 3 核心测试（还原度）

> ⚠️ 使用纪律（同 Round 1，违反则 Step 3 判据失效）：
> 1. **开一个全新会话**，或在同一会话中作为下一条消息发出（二选一，但必须记录是哪种）。
> 2. **只发这段 prompt，不要附加任何东西。**
> 3. **不要重新粘贴素材。** 它必须只用自己上一轮产出的风格指南来写。
>    —— 给了素材＝让它抄，不是让它还原。这是 Step 3 成立的前提。
> 4. 拿到回复后原样存进 `03-raw-output/run-02.txt`。

---

## 复制以下全部内容

```text
Now use ONLY the style guide you just produced.

Do not re-read the original samples. Do not quote them. Do not ask me for them.
Write from the guide alone.

Task: write a 100-word vlogbrothers-style opening blurb for this fictional video.

  Title: "I Tested an AI Note-Taking App That Claims Perfect Lecture Summaries"
  Situation: The app consistently mislabels my roommate as the professor,
  and once summarized an entire hour of me coughing as
  "Key concept: respiratory health."

Rules:
- 90 to 110 words. Count them.
- Output the blurb ONLY. No preamble, no explanation, no headings,
  no labels, no word count stated.
- Use whatever devices from your guide you think apply.
```

---

## 为什么要这样设计

| 设计 | 防的是什么 |
|---|---|
| **不重发素材** | 防止它直接改写原文 → 那是抄，不是还原 |
| **虚构场景**（AI 笔记 App + 室友被认成教授） | 真实 vlogbrothers 素材里没有这个 → 它必须**迁移机制**，不能搬运内容 |
| **90–110 词硬限** | 防止它写长文稀释风格特征；短文本才暴露真实笔迹 |
| **只要 blurb，不要前言** | 防止它用解释性文字伪装成风格还原 |
| **不禁止专有名词** | 故意不设限 —— 如果它硬塞 Nerdfighteria / Pizzamas / John，**那本身就是发现**（说明它只会贴标签，不会迁移机制） |

## 拿到后要记的三件事

| 记什么 | 对应判据 |
|---|---|
| 词数是否在 90–110 | 它守不守指令 |
| 有没有塞真实 vlogbrothers 专有名词 | 「词频指纹」维度 0/1/2 的关键证据 |
| 有没有前言/解释/标签 | 「收尾形状」+ 指令遵循度 |

## 然后

把 run-02 完整内容发我 → 我按 `04-rubric.md` 六维逐项打分（每项附理由，因为**没有理由的分数观众无法复核**）。
