[نسخه‌ی انگلیسی ←](../../../en/projects/project-06-runtime-observability-and-debugging/)

> سخنرانی‌های مرتبط: [سخنرانی ۱۱. Runtime ایجنت را قابل رصد کنید](./../../lectures/lecture-11-why-observability-belongs-inside-the-harness/index.md) · [سخنرانی ۱۲. تحویل تمیز در پایان هر جلسه](./../../lectures/lecture-12-why-every-session-must-leave-a-clean-state/index.md)
> فایل‌های الگو: [templates/](https://github.com/walkinglabs/learn-harness-engineering/blob/main/docs/en/resources/templates/)

# پروژه ۰۶. یک هارنس ایجنت کامل بسازید (Capstone)

## کار شما چیست

این پروژه capstone است. تمام آنچه در پنج پروژه اول یاد گرفتید را جمع‌آوری کنید، یک benchmark کامل اجرا کنید، سپس یک cleanup pass انجام دهید تا تأیید کنید کیفیت قابل نگهداری است.

یک مجموعه تکلیف multi-feature ثابت استفاده کنید که کامل product slice را پوشش می‌دهد: document import، indexing، citation-based Q&A، observability runtime، و readable restartable repo state. ابتدا با weak harness baseline اجرا کنید، سپس با strongest harness شما، سپس یک cleanup و re-run. در نهایت، یک harness ablation experiment انجام دهید — یک بار یک component را حذف کنید و ببینید کدام‌ها واقعاً اهمیت دارند.

## ابزارها

- Claude Code یا Codex
- Git
- Node.js + Electron
- Quality document template
- Evaluator rubric
- تمام اجزای هارنس جمع‌آوری‌شده از پنج پروژه اول

## مکانیسم هارنس

هارنس کامل: تمام مکانیسم‌ها + observability + ablation study

## استفاده از پروژه‌ی بررسی شده

مسیر ریپازیتوری: [`projects/project-06/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-06)

| دایرکتوری | محتوای آن | برای مقایسه کدام چیز |
|------|------|------|
| [`starter/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-06/starter) | کد محصول عمدتاً کامل با سطح هارنس عمدی ضعیف: [`AGENTS.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-06/starter/AGENTS.md) پایه، بدون `feature_list.json`، بدون `session-handoff.md`، بدون clean-state checklist. | مشاهدات baseline weak-harness دستی. starter عمدی شامل اسکریپت‌های benchmark نیست. |
| [`solution/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-06/solution) | سطح harness کامل: [`AGENTS.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-06/solution/AGENTS.md)، [`CLAUDE.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-06/solution/CLAUDE.md)، [`feature_list.json`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-06/solution/feature_list.json)، [`init.sh`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-06/solution/init.sh)، [`session-handoff.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-06/solution/session-handoff.md)، [`clean-state-checklist.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-06/solution/clean-state-checklist.md)، اسناد quality/evaluator، اسکریپت‌های benchmark و cleanup. | [`projects/project-06/solution/scripts/benchmark.sh`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-06/solution/scripts/benchmark.sh) و [`projects/project-06/solution/scripts/cleanup-scanner.sh`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-06/solution/scripts/cleanup-scanner.sh) را اجرا کنید، سپس مدارک quality-document را مقایسه کنید. |

برخلاف پروژه‌های قبلی، starter capstone عمدتاً قابلیت‌های محصول گمشده‌ای ندارد. شکاف اصلی هارنس عامل‌کننده اطراف برنامه است.
