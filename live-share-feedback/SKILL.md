---
name: live-share-feedback
description: Generate short Chinese host-style spoken feedback for a classmate's live sharing session. Use when the user needs an immediate口播点评,主持人串场反馈, post-share verbal comment, or a brief sentence to say before inviting questions.
---

# Live Share Feedback

## Goal

Create a short line the host can say right after a classmate finishes sharing. The output should sound natural when read aloud, quickly affirm the speaker, and smoothly move the room into questions or the next segment.

Default to 30-80 Chinese characters. Keep it spoken, warm, and light.

## Workflow

1. Identify the sharer, topic, and 1-2 strongest visible highlights.
2. Pick only what can be said confidently from the transcript or notes.
3. Write a spoken comment, not a written review.
4. If useful, add one short audience prompt such as "大家有问题可以直接开麦".
5. Review by reading it aloud mentally. If it sounds like a report, rewrite.

## What To Notice

Prioritize live-friendly signals:

- Topic hook: Is the topic fresh, practical, close to recent work, or easy to spark questions?
- Clarity: Did the speaker make the subject easy to understand?
- Concrete detail: Did they use cases, tools, data, demos, screenshots, or personal experience?
- Flow: Was the share smooth enough to praise in the moment?
- Energy: Did the speaker sound prepared, confident, or engaged?
- Audience bridge: Is there a detail worth inviting people to ask about?

Do not try to cover the whole presentation. A live comment should land one clear impression.

## Output Patterns

Default one-line format:

```text
口播：XX同学这次分享很顺，把【主题/工具/案例】讲得比较清楚，尤其是【具体亮点】这一块很有参考价值。大家有问题可以直接开麦。
```

If the user asks for multiple options, give 2-3 variants:

```text
版本一：...
版本二：...
版本三：...
```

## Public Feedback Rules

In live口播, praise first and keep suggestions very light. Do not give sharp criticism in front of the group unless the user explicitly asks for it.

Good live suggestions:

- "后面如果有机会，也可以展开讲讲同类工具对比。"
- "这个话题其实挺适合大家继续追问。"
- "刚才提到的实操流程，大家可以重点问一下。"

Avoid:

- Long content summaries.
- Private coaching comments.
- "你应该..."
- "问题在于..."
- Repeating "结构完整、逻辑清晰、条理分明".

## Tone Rules

Use host language:

- "很棒"
- "这个点很有意思"
- "讲得挺清楚"
- "案例挺鲜活"
- "大家可以顺着这个点问一下"
- "我们可以先听听大家有没有问题"

Avoid AI-flavored patterns:

- "不仅...而且..."
- "不是...而是..."
- "综上所述"
- "值得注意的是"
- "整体而言"
- "进一步提升"

## Final Review

Before final output, check:

- Could a host read this naturally in one breath?
- Is it under 80 Chinese characters unless the user asks longer?
- Does it include one real detail from the share?
- Is there no heavy critique?
- Does it smoothly invite questions or transition?
