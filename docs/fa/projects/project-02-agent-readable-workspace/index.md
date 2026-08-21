[نسخه‌ی انگلیسی ←](../../../en/projects/project-02-agent-readable-workspace/)

> سخنرانی‌های مرتبط: [سخنرانی ۰۳. ریپازیتوری را منبع تنحصری خود کنید](./../../lectures/lecture-03-why-the-repository-must-become-the-system-of-record/index.md) · [سخنرانی ۰۴. دستورالعمل‌ها را بین فایل‌ها تقسیم کنید](./../../lectures/lecture-04-why-one-giant-instruction-file-fails/index.md)
> فایل‌های الگو: [templates/](https://github.com/walkinglabs/learn-harness-engineering/blob/main/docs/en/resources/templates/)

# پروژه ۰۲. پروژه را قابل‌خواندگی کنید و از جایی که رفتید ادامه دهید

## کار شما چیست

"خوانایی" را به ریپازیتوری اضافه کنید تا یک ایجنت جدید بتواند ساختار پروژه را سریع درک کند، پیشرفت فعلی را بداند، و کار را ادامه دهد. به طور مشخص: document import، document detail view، و local persistence را پیاده‌سازی کنید، در طول دو جلسه تکمیل شود.

آن را دو بار از دایرکتوری‌های بررسی شده اجرا می‌کنید: اول‌اً با فضای کاری starter نازک‌تر و بدون `session-handoff.md`، دوم با shape solution که دارای `ARCHITECTURE.md`، `PRODUCT.md`، و `session-handoff.md` بسط یافته است.

## ابزارها

- Claude Code یا Codex
- Git
- Node.js + Electron

## مکانیسم هارنس

فضای کاری قابل‌خواندگی برای ایجنت + فایل‌های وضعیت پایدار

## استفاده از پروژه‌ی بررسی شده

مسیر ریپازیتوری: [`projects/project-02/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-02)

| دایرکتوری | محتوای آن | برای مقایسه کدام چیز |
|------|------|------|
| [`starter/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-02/starter) | کد پروژه ۰۱ به علاوه document import، detail view، و persistence نامکمل. اسناد وجود دارند اما بطور عمدی نازک‌تر هستند، و `session-handoff.md` وجود ندارد. | چقدر یک جلسه‌ی ایجنت دوم بازاب‌کاری می‌کند. |
| [`solution/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-02/solution) | همان بخش تکمیل شده، با اسناد بسط یافته تحت [`projects/project-02/solution/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-02/solution) (به علاوه [`feature_list.json`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-02/solution/feature_list.json) و [`session-handoff.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-02/solution/session-handoff.md)). | آیا یک جلسه‌ی fresh می‌تواند از وضعیت ریپازیتوری بدون context کلامی ادامه دهد. |

قابلیت‌های محصول عبارت‌اند از document import، بارگذاری کامل document detail/content، و persistence در طول restart. قابلیت هارنس فضای کاری قابل‌خواندگی برای تحویل است.
