# 每日分享总结 Skill

这个仓库包含三个 Codex skill，用来把同学每日分享的转写或会议纪要整理成不同场景下的反馈。

- `daily-share-feedback`: 生成可直接发群的「总结 / 点评 / 建议」。
- `live-share-feedback`: 生成主持人现场可口播的短点评。
- `share-feedback-review`: 生成更完整的私下复盘点评。

三个 skill 共用同一套底层判断：先分析选题、内容、结构、证据、表达和可提升点，再只挑最值得说的内容输出。默认要求说人话，避免模板化表扬和常见 AI 口癖。

## 建议用法

```text
Use $daily-share-feedback to 根据这场分享转写，写一版可以直接发群的总结、点评和建议。
```

```text
Use $live-share-feedback to 根据这场分享内容，写一句主持人现场可以说的点评。
```

```text
Use $share-feedback-review to 根据这场分享转写，写一份给同学看的复盘点评。
```
