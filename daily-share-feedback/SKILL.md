---
name: daily-share-feedback
description: Generate concise Chinese feedback for daily student sharing sessions from transcripts, meeting notes, rough summaries, or audio-derived text. Use when the user asks for a group-sendable share summary, short comment, presenter feedback, WeChat group feedback, or "总结/点评/建议" after a classmate's daily presentation.
---

# Daily Share Feedback

## Goal

Turn one daily sharing session into a short group-ready note. The output should help the sharer feel seen, help the group remember what was shared, and leave one useful improvement direction without sounding like a report.

Default to a warm WeChat-group tone: concrete, natural, brief, and easy to send as-is.

## Workflow

1. Identify the main sharer, topic, and audience context. Ignore waiting-room chat, upload reminders, and host housekeeping unless it affects delivery.
2. Extract the real content: topic, core claims, examples, data, tools, cases, workflow, conclusions, and any memorable detail.
3. Evaluate the presentation with the rubric below, but do not output every dimension.
4. Before writing, choose:
   - 1-2 content points worth summarizing.
   - 2-3 strengths worth praising.
   - 1 main improvement opportunity.
5. Write in the requested format. If no format is requested, use "总结 / 点评 / 建议".
6. Review for human tone before finalizing.

If the input is not a daily sharing session, such as an interview or unrelated long conversation, say that the material does not look like a normal daily share and either ask for the target speaker/topic or adapt only if the user clearly wants that.

## Analysis Rubric

Use these dimensions internally:

- Topic value: Is the topic fresh, useful, relevant, or likely to interest the group?
- Audience fit: Does it connect to what classmates are learning or doing?
- Information freshness: Are the examples, model names, data, or industry signals current enough for the topic?
- Core point: Does the sharer have a clear point of view, not just a list of facts?
- Structure: Is there a clear opening, progression, and closing?
- Evidence: Are there data, cases, demos, screenshots, product usage, or personal experience?
- Comparison: Does the share compare tools, products, markets, or alternatives when useful?
- Practicality: Can listeners take away a method, workflow, resource, or concrete understanding?
- Expression: Is the speech fluent, natural, understandable, and appropriately paced?
- Engagement: Does the share have examples, questions, hooks, or moments that keep people listening?
- Materials: Are PPT/screenshots/demos clear and helpful if mentioned?
- Closing: Does the sharer summarize or land the point?

Use optional dimensions only when relevant:

- Original observation, personal experience, story sense, analogy, concept explanation, technical understanding, business insight, compliance/risk awareness, Q&A handling, time control, stage confidence, and interaction.

## Selection Rules

Only output the strongest evidence-backed points.

Prefer:

- Specific praise tied to the actual share.
- Details that prove you listened: product names, cases, data, process steps, or examples.
- One improvement that will make the next share better.

Avoid:

- Generic praise such as "结构完整、逻辑清晰、条理分明" unless it is paired with specific evidence.
- Vague advice such as "提升专业深度" without saying what to add.
- Repeating the same sentence shape across sections.
- Criticizing every weakness. Pick the biggest useful one.

When facts may be time-sensitive, do not invent exact "latest" claims. If the user asks you to verify current data or name the latest model/tool, check reliable current sources first. Otherwise phrase the suggestion generally, such as "可以补充最新数据或同类工具横向对比".

## Output Format

Default format:

```text
XX同学分享点评

总结：...

点评：...

建议：...
```

Keep the whole output around 150-280 Chinese characters unless the user asks otherwise. Each section should be 1-2 sentences. It is acceptable to omit the title if the user wants a message that can be pasted directly into a group.

## Tone Rules

Write like a real person in a group chat, not like an evaluation form.

Use phrases like:

- "这次切入点挺好"
- "讲得比较顺"
- "案例选得很贴近大家"
- "把流程拆得比较清楚"
- "这个点很加分"
- "后面可以再补一点..."

Avoid AI-flavored patterns:

- "不仅...而且..."
- "不是...而是..."
- "综上所述"
- "值得注意的是"
- "进一步提升专业深度"
- "具有重要意义"
- Repeated "整体...整体..."
- Overloaded three-part praise like "完整、清晰、分明"

Do not over-polish. A slightly conversational sentence is better than a perfect but empty sentence.

## Final Review

Before final output, check:

- Can this be sent to a WeChat group directly?
- Does it mention at least one real detail from the share?
- Is the praise specific enough that another sharer could not receive the same comment unchanged?
- Is there only one main improvement point?
- Did you remove formulaic AI phrasing?
- Does the message sound encouraging without becoming flattering?
