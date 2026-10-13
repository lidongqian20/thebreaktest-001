# The Break Test #01 - Prompt（原始提示词，保存后不得修改）

```text
I'm going to give you raw writing samples from an online channel that's
been running since 2007. Your job is to reverse-engineer the writing
style into a reusable guide.

DO NOT summarize the content. I only care about HOW it is written.

Extract, in this exact order:

1. VOICE — who is talking, and what posture do they take toward the
   reader? (e.g. peer, teacher, conspirator, stressed friend)

2. SENTENCE RHYTHM — short vs long sentence distribution. Where do
   long sentences get cut short? How often?

3. SIGNATURE DEVICES — name every recurring rhetorical device you can
   find, and quote the exact line where it appears. Minimum 5.

4. LEXICAL FINGERPRINT — list the actual words, phrases, parenthetical
   asides, and punctuation habits that repeat across samples. Quote them.

5. HUMOR MECHANISM — what triggers the laughs? Be specific about the
   mechanism, not the topic.

6. STRUCTURAL PATTERN — how do these pieces open and close? What is the
   shape of a typical paragraph?

7. THE ONE THING THAT CANNOT BE COPIED — after all the above, tell me
   which element you think would be hardest to reproduce without the
   original author's lived experience, and why.

Rules:
- Every claim must be backed by a direct quote from the samples.
- If something is inconsistent across the samples, say so. Do not
  average it into a bland rule.
- Do not use the words "engaging", "authentic", "compelling", or
  "resonates".

Here are the samples:

[在此粘贴 Hank Green / vlogbrothers 的原始文案]
```

## ⚠️ 使用纪律

- 上面整段**原样复制**给 ChatGPT。**只允许修改最后一行方括号里的内容**，其余一字不改。
- **不要**先跟 ChatGPT 聊几句再贴 prompt —— 那会让输出受上文污染，破坏「一次跑完」的 Step 2 判据。
- 正确做法：**开一个全新会话**，第一句话就是这段 prompt。
- 如果你必须开新会话（比如忘了改某事），如实记录在 `03-raw-output/run-notes.txt` 里，**不要藏着**。

## 记录区（跑完后填）

| 项 | 值 |
|---|---|
| 实际使用的模型 | （如 GPT-5 / GPT-4o / 其他） |
| 实际粘贴的素材文件 | |
| 发送时间 | |
| 是否全新会话 | 是 / 否 |
