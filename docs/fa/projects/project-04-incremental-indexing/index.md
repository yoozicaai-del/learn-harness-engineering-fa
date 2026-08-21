[نسخه‌ی انگلیسی ←](../../../en/projects/project-04-incremental-indexing/)

> سخنرانی‌های مرتبط: [سخنرانی ۰۷. مرزهای تکلیف واضح برای ایجنت رسم کنید](./../../lectures/lecture-07-why-agents-overreach-and-under-finish/index.md) · [سخنرانی ۰۸. از فهرست قابلیت‌ها برای محدود کردن اعمال ایجنت استفاده کنید](./../../lectures/lecture-08-why-feature-lists-are-harness-primitives/index.md)
> فایل‌های الگو: [templates/](https://github.com/walkinglabs/learn-harness-engineering/blob/main/docs/en/resources/templates/)

# پروژه ۰۴. برای اصلاح رفتار ایجنت از بازخورد Runtime استفاده کنید

## کار شما چیست

رصدپذیری runtime (startup logs، import/indexing logs، error states) و محدودیت‌های معماری برای جلوگیری از نقض لایه متقاطع را اضافه کنید. یک bug runtime برای ایجنت برای اصلاح کاشته کنید.

شما starter و solution بررسی شده را مقایسه می‌کنید: starter تشخیص‌های ضعیف دارد و هیچ اسکریپت guard معماری ندارد، در حالی که solution logs ساختار‌یافته، بررسی‌های مرزی، و اصلاح bug را اضافه می‌کند.

## ابزارها

- Claude Code یا Codex
- Git
- Node.js + Electron

## مکانیسم هارنس

بازخورد runtime + کنترل دامنه‌ی کار + incremental indexing

## استفاده از پروژه‌ی بررسی شده

مسیر ریپازیتوری: [`projects/project-04/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-04)

| دایرکتوری | محتوای آن | برای مقایسه کدام چیز |
|------|------|------|
| [`starter/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-04/starter) | کد پروژه ۰۳ با تشخیص‌های ضعیف. یک عیب indexing کاشته شده می‌تواند chunking فایل‌های بزرگ را ناموفق کند، و هیچ اسکریپت architecture-check وجود ندارد. | چقدر ایجنت برای پیدا کردن علت ریشه بدون سیگنال‌های runtime طول می‌کشد. |
| [`solution/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-04/solution) | Structured logger، اسناد و اسکریپت boundary معماری، logic chunking اصلاح شده، و [`clean-state-checklist.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-04/solution/clean-state-checklist.md). | آیا logs و boundary checks اصلاح را سریع‌تر و کم‌تر تهاجمی می‌کنند. |

فایل‌های مشخص برای بررسی عبارت‌اند از [`projects/project-04/solution/src/services/logger.ts`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-04/solution/src/services/logger.ts)،
[`projects/project-04/solution/scripts/check-architecture.sh`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-04/solution/scripts/check-architecture.sh)،
[`projects/project-04/solution/docs/ARCHITECTURE.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-04/solution/docs/ARCHITECTURE.md)، و
[`projects/project-04/solution/src/services/indexing-service.ts`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-04/solution/src/services/indexing-service.ts).
