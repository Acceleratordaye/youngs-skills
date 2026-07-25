---
name: douyin-technical-account-research
description: Research logged-in Douyin technical accounts, including account identity, linked accounts, video and image-post tutorials, technical claims, product reviews, comments, user feedback, and author replies. Use when the user asks to investigate a technical creator, TradingView indicator, trading or quantitative tool, AI tool, software tutorial, technical product, or related account. Prefer the ChatGPT Desktop built-in browser, apply a scan-classify-deep-dive workflow, use value-based stopping rules, and produce a source-layered Chinese report. Do not switch browser environments unless the user explicitly permits it.
---

# Douyin Technical Account Research

## Operating boundary

Prefer the ChatGPT Desktop built-in browser and the user's existing logged-in Douyin session. If that capability is unavailable, do not automatically switch to a cloud browser, remote agent browser, Edge, or Chrome. State the current environment limitation, explain which parts of the research cannot proceed, and ask for explicit permission before considering another browser environment. Never imply that login state will carry across environments.

Keep the core operating assumption that the target account is researched from an already authenticated Douyin session. If no usable authenticated session is available, pause the live investigation and provide only a scoped preparation plan or analysis of material already supplied by the user.

Account for client differences instead of assuming mobile-app interactions exist everywhere:

- The Douyin mobile app commonly supports tapping an `@account` link in a profile bio.
- The Douyin desktop client may preserve hover state long enough to complete the subsequent click normally.
- Douyin web and the ChatGPT Desktop built-in browser may render the same `@account` as plain text, or may fail to preserve hover state along a normal pointer path from hover to click.
- Treat unstable hover state or a failed normal click path as a possible missing web feature, browser-compatibility issue, or platform frontend interaction defect. Do not default to blaming Agent or user operation.
- Adapt to the current environment and never depend on mobile-only interaction behavior in the built-in browser.

Use only normal business interactions. Do not use complex non-business operations or temporary workarounds to preserve hover state. When normal web interaction is unreliable, switch to search-based verification.

If login expires or Douyin presents a CAPTCHA, security check, device confirmation, or other human verification, stop browsing immediately. Tell the user exactly what is visible and wait for them to complete it. Never attempt to bypass verification.

Do not create APIs, connectors, scraping scripts, or automated bulk collection. Use visible browser interactions and inspect only the material needed for the research question.

Keep a working evidence ledger using `assets/research-notes-template.md`. Use `assets/final-report-template.md` for the deliverable.

## Execution contract

Follow `scan -> classify -> deep dive -> synthesize`.

- Do not play every video, scroll indefinitely, or read repetitive comments.
- Prefer posts containing: 教程、方法、原理、参数、更新、评测、问题、bug、实战、案例.
- When several posts repeat one topic, investigate the most information-dense post and record the others as corroborating or duplicate entries.
- Separate observation from inference. Attach a post title/date or another visible locator to every important claim.
- Distinguish `作者宣传`, `作者教程`, `用户反馈`, and `作者回复`. Never convert promotional language into verified fact.
- If the task becomes long, deliver a useful phase report with completed coverage, provisional findings, gaps, and the next recommended deep dives. Never return only “任务未完成”.

Apply this research priority order:

1. complete tutorials, product documentation, and algorithm explanations;
2. real case demonstrations;
3. technical user feedback and author replies;
4. ordinary promotion and showcase content.

Spend browsing actions on the highest unresolved information value. Re-rank candidates as evidence accumulates.

### Active stopping conditions

End the investigation when all of the following are satisfied:

1. the account identity is confirmed or its remaining uncertainty is clearly bounded;
2. the main relevant content categories have been covered;
3. at least one core tutorial or the best available substitute has been deeply reviewed;
4. the major disputed questions have been answered or explicitly marked unresolved with the missing evidence identified;
5. several consecutive browsing actions produce no new effective information.

Treat “effective information” as evidence that changes a conclusion, adds a reproducible step, resolves a dispute, reveals a limitation, or improves confidence. Stop when marginal information value is low; do not pursue infinite completeness or maximize item count.

## 1. Confirm the account

Use the user's supplied account name, Douyin ID, and target topic.

1. Compare the visible display name and Douyin ID with the target.
2. Record the bio, account positioning, visible credentials or disclosures, follower-facing product claims, and relevant links.
3. Note name collisions or ambiguity. If identity cannot be confirmed from visible evidence, label it uncertain rather than guessing.
4. Inspect any `@关联账号` in the bio and preserve its exact visible account name in the notes.
5. Test the visible `@account` through the normal interaction path: click it once and, when relevant, hover over it once to check for a stable preview or normal follow-up click target. If either interaction reveals or opens a usable profile target, verify that profile before including it in scope.
6. If the normal click path fails or applicable hover state cannot be maintained normally, classify the result as a possible client interaction limitation. Do not assume Agent error or user error.
7. Do not repeat clicks or hovers indefinitely, refresh the page to retry, or use complex non-business interactions to keep the state alive. Switch directly to Douyin's internal search using the recorded account name.
8. Compare search candidates by exactly matching account name, reciprocal bio association, and content-topic consistency. Use visible mutual-follow or author-relationship information as additional evidence when available. Treat every match as evidence, not automatic proof.
9. If the search still does not establish identity, record: `发现简介关联账号，但当前浏览器环境无法通过正常交互验证跳转。` Keep the candidate unconfirmed and do not force a match.

Apply a maximum of one click and one applicable hover attempt to any profile-bio `@account`. Once the normal path has no effect, switch methods; never loop clicks, hovers, refreshes, or repeated verification of the same unsupported function.

## 2. Build a content index

Scan the account page before opening posts. Stop once the visible/relevant content is sufficiently classified; do not chase an arbitrary completeness target.

For each potentially relevant item, record:

- title or visible opening text;
- publish date or visible relative time;
- format: video, image post, live replay, or other;
- topic keywords;
- relevance: high, medium, or low;
- why it matters to the target question;
- status: indexed, opened, deeply reviewed, or duplicate.

Rank candidates by relevance, technical density, evidence value, recency when updates matter, and presence of substantive comments. Select a small deep-dive set that covers distinct subtopics.

## 3. Research high-value videos

For each selected video:

1. Read the title and description.
2. Inspect available captions/subtitles and on-screen text.
3. Play only as needed to understand the explanation, sequence, demonstration, or disputed behavior.
4. Observe software interfaces, settings, charts, indicators, parameters, warnings, before/after states, and actual operations.
5. Record timestamps for decisive demonstrations when the interface exposes them.

If captions/subtitles are missing, do not skip a high-value video. Investigate in this order:

1. text visible in the video frames;
2. the author's title and description;
3. the demonstrated actions and visible outcomes;
4. technical discussion in the comments;
5. key video segments played only when necessary.

Mark conclusions derived without subtitles and lower confidence when speech-dependent details cannot be verified. If subtitles conflict with the visible demonstration, preserve both accounts, identify the exact conflict, and prefer directly observable behavior for claims about what the software actually did.

Extract:

- the tutorial outcome and prerequisites;
- exact operating steps and parameter choices;
- the stated technical mechanism;
- the author's interpretation or opinion;
- facts directly demonstrated or otherwise verifiable;
- applicable scenarios, limitations, failure conditions, and omitted assumptions.

Do not write only “作者介绍了 X”. Explain how to do it, why the author says it works, where it applies, and what constrains it. If subtitles conflict with the visible demonstration, record the conflict.

## 4. Research image posts

Never infer an image post from its cover alone.

1. Open the post.
2. Browse every image in order.
3. Read legible text embedded in each image.
4. Read the post body.
5. Inspect relevant comments and author replies.

Analyze software screenshots, parameter panels, K-line charts, tutorial flowcharts, comparison tables, and result screenshots. State what the image visibly supports and what it cannot prove. Treat isolated performance screenshots or selected examples as promotional evidence unless methodology and reproducibility are shown.

## 5. Research comments selectively

Ignore praise-only and repetitive comments such as “牛逼”, “学到了”, and “老师666”.

Prioritize:

- setup and parameter questions;
- reports of errors, inconsistent signals, repainting, future functions, live-versus-backtest differences, compatibility, cost, refunds, or support;
- requests for the reasoning behind a judgment;
- author replies that clarify, qualify, contradict, or acknowledge a problem.

For each useful thread, record the commenter claim/question, author reply if present, associated post, and evidence category. Do not treat a single comment as representative user consensus. Note repeated independent reports only when they are visibly distinct.

## 6. Evaluate tutorials and products

Maintain four evidence lanes:

| Lane | Meaning | Treatment |
|---|---|---|
| A. 作者宣传 | Sales language, performance claims, testimonials selected by the author | Unverified unless independently demonstrated |
| B. 作者教程 | Methods, steps, explanations, demonstrations | Assess clarity, reproducibility, assumptions, and technical soundness |
| C. 用户反馈 | Questions, success/failure reports, complaints | Anecdotal; assess specificity and repetition |
| D. 作者回复 | Clarifications, fixes, limitations, rebuttals | Attribute directly and compare with the original claim |

Evaluate:

- what problem the product/tool solves;
- workflow, inputs, outputs, and dependencies;
- transparency of parameters and logic;
- reproducibility and visible evidence;
- risk of repainting, future data, hindsight bias, cherry-picking, or backtest/live mismatch when relevant;
- pricing/value only when visible and current in the browser;
- support quality inferred from concrete replies, not response-count impressions;
- who benefits, who should avoid it, and what should be tested before purchase.

For trading content, never imply profitability from screenshots or author claims. Explicitly examine signal timing, repainting/future-function concerns, parameter sensitivity, fees/slippage, sample period, and real-time versus historical behavior when evidence permits.

## 7. Apply the trading software and indicator module when relevant

Activate this optional module when the subject involves TradingView, trading indicators, quantitative software, technical-analysis tools, or automated trading tools.

Check and record evidence for:

- repainting and whether previously plotted signals change or disappear;
- future-function or look-ahead data use;
- consistency between historical charts and real-time charts;
- signal drift after new bars or refreshed data;
- parameter sensitivity and whether small changes materially alter results;
- signal confirmation time: intrabar, bar close, later bars, or unspecified;
- dependence on manual interpretation or discretionary filtering;
- selective examples, cherry-picked periods, and success-only demonstrations;
- differences between backtest, replay, paper trading, and live execution;
- implementation constraints such as data source, timeframe, alert timing, latency, order handling, fees, and slippage when relevant.

Separate `理论方法` from `软件工程实现`:

- Evaluate the theory as the conceptual rule, hypothesis, or analytical method.
- Evaluate the implementation as code behavior, data handling, platform constraints, parameter defaults, alert logic, and execution timing.
- Do not treat a flawed implementation as proof that the theory is false.
- Do not treat a plausible theory as proof that the software implements it correctly.
- State which layer each finding supports and what test would distinguish them.

## 8. Synthesize the report

Write in Chinese unless the user asks otherwise. Use the following sections in order:

# 执行摘要
# 账号介绍
# 内容目录
# 核心教程总结
# 产品/工具分析
# 用户真实反馈
# 作者技术解释
# 存在的问题
# 是否值得学习/购买
# 初学者学习路线

Within relevant sections, label claims with the evidence lane and a confidence level:

- `高`: directly visible, consistently demonstrated, or supported by multiple concrete items;
- `中`: plausible and specifically supported, but incomplete;
- `低`: promotional, anecdotal, ambiguous, or not reproducible from visible material.

Include a coverage note stating the accounts, date range or visible page range, posts deeply reviewed, image sets fully browsed, and comment threads sampled. List unresolved questions and the shortest next verification step.

Give a conditional purchase judgment rather than a blanket endorsement. Separate “worth learning from free content” from “worth paying for the product”.

## Beginner learning route

Turn the strongest tutorials into an ordered route:

1. prerequisites and terminology;
2. basic setup;
3. one reproducible beginner exercise;
4. parameter or mechanism understanding;
5. validation against counterexamples or live behavior;
6. advanced use and risk controls.

Link each stage to an indexed post title/date or visible locator. Do not recommend advanced paid material before the learner can independently reproduce the basics.

## Completion checklist

Before answering, confirm:

- account identity and relevant linked accounts were checked, or an unverified bio association was explicitly recorded;
- the homepage was indexed before deep dives;
- selected videos were examined beyond title/cover;
- every selected image post was browsed through all images;
- comments were filtered for technical value;
- claims were separated into the four evidence lanes;
- limitations and contradictory evidence were retained;
- the report contains actionable steps, not topic-only summaries;
- incomplete coverage is disclosed with a useful phase result.
- active stopping conditions were checked and the stop reason is recorded.
