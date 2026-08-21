[نسخه‌ی انگلیسی ←](../../../en/projects/project-05-grounded-qa-verification/)

> سخنرانی‌های مرتبط: [سخنرانی ۰۹. ایجنت را از اعلام پیروزی زودرس منصرف کنید](./../../lectures/lecture-09-why-agents-declare-victory-too-early/index.md) · [سخنرانی ۱۰. تنها یک اجرای full-pipeline به عنوان راستی‌آزمایی واقعی به حساب می‌آید](./../../lectures/lecture-10-why-end-to-end-testing-changes-results/index.md)
> فایل‌های الگو: [templates/](https://github.com/walkinglabs/learn-harness-engineering/blob/main/docs/en/resources/templates/)

# پروژه ۰۵. ایجنت را برای راستی‌آزمایی کار خود تهیه کنید

## کار شما چیست

جداسازی نقش را پیاده‌سازی کنید — یک generator که پیاده‌سازی می‌کند، یک ارزیاب که بررسی می‌کند، و اختیاری یک planner. سه بار اجرا کنید تا اثر هر نقش اضافه‌شده را اندازه‌گیری کنید.

یک ارتقاء قابلیت مختص (چند گفتگو، طراحی مجدد citation panel، یا filtering سند) را انتخاب کنید و در تمام اجراها ثابت نگاه دارید.

## ابزارها

- Claude Code یا Codex
- Git
- Node.js + Electron

## مکانیسم هارنس

خود-راستی‌آزمایی + grounded Q&A + تکمیل مبتنی‌بر مدارک

## استفاده از پروژه‌ی بررسی شده

مسیر ریپازیتوری: [`projects/project-05/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-05)

| دایرکتوری | محتوای آن | برای مقایسه کدام چیز |
|------|------|------|
| [`starter/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-05/starter) | برنامه‌ی مبتنی‌بر پروژه ۰۴ قبل از ارتقاء conversation-history. | نقطه شروع اگر می‌خواهید سه variant را خودتان دوباره اجرا کنید. |
| [`solution/single-role/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-05/solution/single-role) | یک ایجنت برنامه‌ریزی، پیاده‌سازی، و خود-بررسی می‌کند. | امتیاز [`evaluator-rubric.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-05/solution/single-role/evaluator-rubric.md) 1.6/5 و نقص‌های فهرست‌شده. |
| [`solution/gen-eval/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-05/solution/gen-eval) | Generator به علاوه ارزیاب با مدارک revision. | امتیاز [`evaluator-rubric.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-05/solution/gen-eval/evaluator-rubric.md) 3.3/5 و یادداشت‌های revision. |
| [`solution/plan-gen-eval/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-05/solution/plan-gen-eval) | Planner به علاوه generator به علاوه ارزیاب. | [`sprint-contract.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-05/solution/plan-gen-eval/sprint-contract.md)، امتیاز [`evaluator-rubric.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-05/solution/plan-gen-eval/evaluator-rubric.md) 4.9/5. |

قابلیت بررسی‌شده multi-turn Q&A conversation history است. این قابلیت را در تمام سه variant ثابت نگاه دارید تا تنها متغیر جداسازی نقش باشد.
