# AI Workspace

این ریپو محل نگهداری دارایی‌های پایدار مربوط به کار با AI است: promptها، contextها، agent specها، workflowها، تصمیم‌ها، templateها و خروجی‌های مهم.

هدف این ریپو ذخیره‌کردن چت‌های خام نیست. هدف این است که چیزهای قابل استفاده مجدد از ChatGPT، Claude، Gemini، agentها و ابزارهای دیگر استخراج، مرتب، نسخه‌بندی و دوباره استفاده شوند.

---

## اصل اصلی

AIها محیط اجرا هستند.  
این ریپو محل حقیقت است.

```text
ChatGPT = execution environment
Claude = execution environment
Agents = execution environment
GitHub repo = source of truth
```

چت‌ها موقتی‌اند.  
دارایی‌های استخراج‌شده پایدارند.

```text
Chat → Distill → Save → Version → Reuse
```

---

## چه چیزی را اینجا ذخیره می‌کنیم؟

### ذخیره شود

- promptهای قابل استفاده مجدد
- context packهای پروژه‌ها
- agent specها
- workflowهای چندمرحله‌ای
- decision logها
- output templateها
- handoff packetها برای انتقال بین ChatGPT، Claude و ابزارهای دیگر
- مثال‌های تست‌شده برای promptها
- خلاصه‌ی خروجی‌های مهم

### ذخیره نشود

- چت خام
- جواب‌های یک‌بارمصرف
- ترجمه‌ها یا اصلاحات کوچک لحظه‌ای
- خروجی‌های موقت
- فایل‌های حجیم
- PDF، تصویر، اکسل یا فایل‌های خامی که فقط مصرف شده‌اند
- هر چیزی که احتمال استفاده مجدد پایینی دارد

قاعده:

```text
اگر احتمال reuse کمتر از ۲۰٪ است، ذخیره نکن.
```

---

## ساختار ریپو

```text
ai-workspace/
  inbox/
  prompts/
  contexts/
  agents/
  workflows/
  templates/
  decisions/
  outputs/
  examples/
```

### `inbox/`

محل موقت برای چیزهای خام و هنوز دسته‌بندی‌نشده.

مثال:

```text
inbox/2026-01-15-chatgpt-pricing-idea.md
```

هر چیزی که فعلاً ارزش دارد ولی هنوز معلوم نیست کجا باید برود، اول وارد `inbox/` می‌شود.

---

### `prompts/`

محل نگهداری promptهای قابل استفاده مجدد.

مثال:

```text
prompts/research/market-analysis.v1.md
prompts/sales/cold-email.v2.md
prompts/writing/landing-page-review.v1.md
prompts/analysis/file-summary.v1.md
```

prompt باید مستقل، قابل فهم و قابل اجرا باشد.

---

### `contexts/`

محل نگهداری اطلاعات زمینه‌ای ثابت.

Context با prompt فرق دارد.

Prompt یعنی دستور انجام کار.  
Context یعنی اطلاعات زمینه‌ای که AI باید بداند.

مثال:

```text
contexts/company/brand-voice.v1.md
contexts/projects/product-x/context.v1.md
contexts/personal/preferences.v1.md
```

---

### `agents/`

محل نگهداری تعریف agentها.

Agent داخل یک پلتفرم ممکن است قابل انتقال کامل نباشد، اما spec آن باید قابل انتقال باشد.

مثال:

```text
agents/portable/research-analyst.v1.md
agents/chatgpt/content-strategist.v1.md
agents/claude/editorial-reviewer.v1.md
```

---

### `workflows/`

محل نگهداری فرایندهای چندمرحله‌ای.

مثال:

```text
workflows/content-production/blog-production.v1.md
workflows/research/competitor-analysis.v1.md
workflows/product/feature-discovery.v1.md
```

workflow یعنی ترتیب استفاده از چند prompt، context، agent یا ابزار.

---

### `templates/`

قالب‌های استاندارد برای فایل‌های پرتکرار.

مثال:

```text
templates/prompt-template.md
templates/context-pack-template.md
templates/agent-spec-template.md
templates/handoff-packet-template.md
templates/decision-log-template.md
templates/workflow-template.md
```

---

### `decisions/`

تصمیم‌های مهمی که بعداً باید قابل بازیابی باشند.

مثال:

```text
decisions/2026/2026-01-15-positioning-model.md
decisions/2026/2026-01-20-pricing-direction.md
```

decision log باید توضیح دهد چه تصمیمی گرفته شد، چرا گرفته شد، چه گزینه‌هایی رد شدند و نتیجه چه بود.

---

### `outputs/`

خروجی‌های نهایی مهم.

مثال:

```text
outputs/2026/2026-01-15-market-analysis-product-x.md
outputs/2026/2026-01-20-landing-page-copy-v1.md
```

خروجی‌های موقت نباید اینجا ذخیره شوند.

---

### `examples/`

مثال‌های تست‌شده برای promptها و workflowها.

مثال:

```text
examples/prompt-tests/market-analysis/input.good-fit.md
examples/prompt-tests/market-analysis/output.good-fit.md
examples/prompt-tests/market-analysis/input.bad-fit.md
examples/prompt-tests/market-analysis/output.bad-fit.md
```

---

## نام‌گذاری فایل‌ها

فرمت پیشنهادی:

```text
prompt.[domain].[task].v[number].md
context.[project].[topic].v[number].md
agent.[function].v[number].md
workflow.[process].v[number].md
decision.[date].[topic].md
output.[date].[topic].md
```

مثال:

```text
prompt.research.market-analysis.v1.md
prompt.sales.cold-email.v2.md
context.company.brand-voice.v3.md
agent.research-analyst.v1.md
workflow.blog-production.v2.md
decision.2026-01-15-pricing-model.md
output.2026-01-15-market-analysis.md
```

---

## قالب Prompt

```markdown
# prompt.domain.task.v1

## Purpose

این prompt برای چه کاری استفاده می‌شود.

## Use When

چه زمانی باید از این prompt استفاده شود.

## Inputs

- input 1
- input 2
- input 3

## Prompt

متن اصلی prompt اینجا قرار می‌گیرد.

## Output Format

فرمت دقیق خروجی مورد انتظار.

## Works Best In

- ChatGPT:
- Claude:
- Other:

## Notes

نکات اجرایی، ضعف‌ها، محدودیت‌ها.

## Version History

- v1: نسخه اولیه
```

---

## قالب Context Pack

```markdown
# context.project.topic.v1

## Project / Entity

نام پروژه، شرکت، محصول یا موضوع.

## Goal

هدف کلی.

## Background

اطلاعات زمینه‌ای.

## Audience

مخاطب یا کاربر هدف.

## Constraints

محدودیت‌ها.

## Current Decisions

تصمیم‌های فعلی.

## Terms We Use

اصطلاحاتی که باید استفاده شوند.

## Terms We Avoid

اصطلاحاتی که نباید استفاده شوند.

## Files / Links

لینک‌ها یا فایل‌های مرتبط.

## Open Questions

ابهام‌ها و سؤال‌های باز.
```

---

## قالب Agent Spec

```markdown
# agent.function.v1

## Mission

ماموریت اصلی agent.

## Responsibilities

- مسئولیت 1
- مسئولیت 2
- مسئولیت 3

## Inputs Needed

- input 1
- input 2
- input 3

## Tools Needed

- Web research
- File reading
- Spreadsheet editing
- Calendar
- Email
- Slack
- Other

## Operating Rules

- قانون 1
- قانون 2
- قانون 3

## Output Format

فرمت خروجی استاندارد.

## Platform Notes

### ChatGPT

نکات مربوط به پیاده‌سازی در ChatGPT.

### Claude

نکات مربوط به پیاده‌سازی در Claude.

### Other Platforms

نکات مربوط به ابزارهای دیگر.

## Safety / Approval Rules

کارهایی که نیاز به تأیید دستی دارند.

## Version History

- v1: نسخه اولیه
```

---

## قالب Workflow

```markdown
# workflow.process-name.v1

## Purpose

این workflow چه کاری انجام می‌دهد.

## Inputs

ورودی‌های لازم.

## Steps

### Step 1: Research

Run:

```text
prompt.research.topic-map.v1
```

### Step 2: Strategy

Run:

```text
prompt.strategy.angle-selection.v1
```

### Step 3: Draft

Run:

```text
prompt.writing.draft.v1
```

### Step 4: Review

Run:

```text
prompt.editing.review.v1
```

## Outputs

خروجی‌های نهایی.

## Quality Checks

چک‌های لازم قبل از نهایی‌سازی.

## Notes

نکات اجرایی.
```

---

## قالب Handoff Packet

برای انتقال کار از ChatGPT به Claude، از Claude به ChatGPT، یا از یک agent به ابزار دیگر از این قالب استفاده شود.

```markdown
# AI Handoff Packet

## Goal

کار نهایی چیست.

## Current State

تا اینجا چه انجام شده است.

## Key Decisions

تصمیم‌های گرفته‌شده.

## Important Context

زمینه‌ای که ابزار بعدی باید بداند.

## Source Output

خروجی قبلی یا خلاصه آن.

## What I Need From You

کار دقیق بعدی.

## Constraints

محدودیت‌ها.

## Desired Output Format

فرمت خروجی مورد انتظار.
```

---

## قالب Decision Log

```markdown
# decision.YYYY-MM-DD.topic

## Decision

تصمیم نهایی.

## Context

زمینه‌ای که باعث این تصمیم شد.

## Options Considered

### Option 1

توضیح.

### Option 2

توضیح.

### Option 3

توضیح.

## Why This Decision

دلیل انتخاب.

## Rejected Alternatives

گزینه‌های ردشده و دلیل رد.

## Implications

اثر این تصمیم روی کارهای آینده.

## Review Date

تاریخ احتمالی بازبینی.
```

---

## روش کار استاندارد

### ۱. کار داخل AI انجام می‌شود

مثلاً در ChatGPT، Claude یا یک agent.

### ۲. چت خام ذخیره نمی‌شود

چت خام معمولاً پر از noise است.

### ۳. از AI خروجی distilled گرفته می‌شود

در پایان یک چت مهم، از این prompt استفاده شود:

```text
از این گفتگو فقط دارایی‌های قابل استفاده مجدد را استخراج کن:

1. Prompts
2. Context packs
3. Agent specs
4. Workflow steps
5. Decisions
6. Output templates
7. Open questions

فرمت خروجی Markdown باشد.
چیزهای تکراری، مکالمه‌ای، کم‌ارزش و یک‌بارمصرف را حذف کن.
```

### ۴. فقط خروجی تمیز وارد ریپو می‌شود

نه کل چت.

### ۵. تغییرات commit می‌شود

```bash
git add .
git commit -m "update ai workspace assets"
git push
```

---

## Prompt برای تبدیل چت به فایل‌های ریپو

در پایان یک گفتگوی مفید، این را به AI بده:

```text
این گفتگو را به فایل‌های قابل ذخیره در ریپوی ai-workspace تبدیل کن.

خروجی را دقیقاً در این ساختار بده:

## File: prompts/[domain]/[name].v1.md
[content]

## File: contexts/[project]/[name].v1.md
[content]

## File: agents/[platform-or-portable]/[name].v1.md
[content]

## File: workflows/[domain]/[name].v1.md
[content]

## File: decisions/YYYY/YYYY-MM-DD-[topic].md
[content]

فقط فایل‌هایی را تولید کن که واقعاً ارزش استفاده مجدد دارند.
چت خام، توضیح اضافه، مقدمه و محتوای کم‌ارزش را حذف کن.
```

---

## Prompt برای انتقال کار به Claude یا ChatGPT

```text
بر اساس اطلاعات زیر یک AI Handoff Packet بساز.

هدف:
[goal]

وضعیت فعلی:
[current state]

تصمیم‌های گرفته‌شده:
[key decisions]

خروجی قبلی:
[source output]

کار بعدی:
[next task]

محدودیت‌ها:
[constraints]

فرمت خروجی موردنیاز:
[desired output format]

خروجی را Markdown بده.
```

---

## قانون تصمیم‌گیری برای ذخیره‌سازی

```text
آیا دوباره استفاده می‌شود؟
نه → ذخیره نکن

آیا فقط یک بخشش مهم است؟
بله → فقط همان بخش را extract کن

آیا روی تصمیم یا workflow آینده اثر دارد؟
بله → ذخیره کن

آیا باید نسخه‌بندی شود؟
بله → Git

آیا فقط فایل نهایی است؟
بله → outputs یا ابزار فایل، نه لزوماً Git

آیا هنوز خام و نامشخص است؟
بله → inbox
```

---

## Commit Guidelines

برای تغییرات عمومی:

```bash
git commit -m "update ai workspace assets"
```

برای prompt جدید:

```bash
git commit -m "add market research prompt v1"
```

برای context جدید:

```bash
git commit -m "add product context pack"
```

برای workflow جدید:

```bash
git commit -m "add blog production workflow"
```

برای تصمیم مهم:

```bash
git commit -m "record pricing model decision"
```

---

## Review Cadence

### روزانه یا بعد از session مهم

- خروجی‌های مهم را extract کن
- فایل‌های لازم را update کن
- commit بزن

### هفتگی

- `inbox/` را پاکسازی کن
- promptهای تکراری را merge کن
- فایل‌های بی‌مصرف را حذف کن
- contextهای قدیمی را update کن
- تصمیم‌های مهم را به `decisions/` منتقل کن

### ماهانه

- promptهای اصلی را بازبینی کن
- agent specها را به‌روزرسانی کن
- workflowهای پرتکرار را تمیز کن
- فایل‌های archive یا deprecated را مشخص کن

---

## اصل نهایی

چت را ذخیره نکن.  
ارزش استخراج‌شده از چت را ذخیره کن.

```text
Do not manage conversations.
Manage reusable knowledge assets.
```
