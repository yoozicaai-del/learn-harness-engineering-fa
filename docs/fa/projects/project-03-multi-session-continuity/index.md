[نسخه‌ی انگلیسی ←](../../../en/projects/project-03-multi-session-continuity/)

> سخنرانی‌های مرتبط: [سخنرانی ۰۵. Context را در سراسر جلسات زنده نگاه دارید](./../../lectures/lecture-05-why-long-running-tasks-lose-continuity/index.md) · [سخنرانی ۰۶. قبل از هر جلسه‌ی ایجنت initialization کنید](./../../lectures/lecture-06-why-initialization-needs-its-own-phase/index.md)
> فایل‌های الگو: [templates/](https://github.com/walkinglabs/learn-harness-engineering/blob/main/docs/en/resources/templates/)

# پروژه ۰۳. ایجنت را در سراسر بازآغازهای جلسه کارکنند نگاه دارید

## کار شما چیست

کنترل دامنه‌ی کار و دروازه‌های راستی‌آزمایی را به ایجنت اضافه کنید. document chunking، metadata extraction، نمایش پیشرفت indexing، و جریان Q&A مبتنی‌بر citation را پیاده‌سازی کنید. از `feature_list.json` برای ردیابی status قابلیت استفاده کنید — یک قابلیت در یک زمان، بدون علامت‌گذاری "pass" بدون مدارک راستی‌آزمایی.

شما starter و solution بررسی شده را مقایسه می‌کنید: starter تنها سطح ردیابی اولیه دارد، در حالی که solution artifact‌های restart و handoff سخت‌گیرانه‌تری را اضافه می‌کند که حول همان فهرست قابلیت است.

## ابزارها

- Claude Code یا Codex
- Git
- Node.js + Electron

## مکانیسم هارنس

Progress log + تحویل جلسه + تداوم چند جلسه‌ای + راستی‌آزمایی یک قابلیت در یک زمان

## استفاده از پروژه‌ی بررسی شده

مسیر ریپازیتوری: [`projects/project-03/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-03)

| دایرکتوری | محتوای آن | برای مقایسه کدام چیز |
|------|------|------|
| [`starter/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-03/starter) | کد پروژه ۰۲ با indexing و grounded QA هنوز نامکمل. یک starter [`feature_list.json`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-03/starter/feature_list.json) دارد، اما artifact‌های restart/handoff نهایی را ندارد. | آیا ایجنت در سراسر چندین قابلیت drift می‌کند یا بعد از restart state را از دست می‌دهد. |
| [`solution/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-03/solution) | chunking، metadata، index status، و citation-based QA تکمیل شده، به علاوه [`init.sh`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-03/solution/init.sh)، [`session-handoff.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-03/solution/session-handoff.md)، [`claude-progress.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-03/solution/claude-progress.md)، و [`clean-state-checklist.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-03/solution/clean-state-checklist.md). | آیا هر قابلیت دارای مدارک مشخص راستی‌آزمایی قبل از علامت‌گذاری passing است. |

این پروژه یک تمرین عام "multi-session" نیست. راه‌حل بررسی شده به چهار قابلیت محصول مشخص نقشه می‌رود: document chunking، metadata extraction، indexing status UI، و grounded Q&A با citations.
