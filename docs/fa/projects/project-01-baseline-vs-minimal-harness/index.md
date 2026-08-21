[نسخه‌ی انگلیسی ←](../../../en/projects/project-01-baseline-vs-minimal-harness/)

> سخنرانی‌های مرتبط: [سخنرانی ۰۱. مدل‌های قوی به معنای اجرای قابل‌اعتماد نیست](./../../lectures/lecture-01-why-capable-agents-still-fail/index.md) · [سخنرانی ۰۲. منظور هارنس واقعاً چیست](./../../lectures/lecture-02-what-a-harness-actually-is/index.md)
> فایل‌های الگو: [templates/](https://github.com/walkinglabs/learn-harness-engineering/blob/main/docs/en/resources/templates/)

# پروژه ۰۱. فقط پرامپت در مقابل قوانین اول: تفاوت چقدر است

## کار شما چیست

یک shell برنامه‌ی پایگاه‌داده‌ی Electron کمینه بسازید — پنجره‌ای با فهرست سند در سمت چپ، پنل Q&A در سمت راست، و یک دایرکتوری داده‌های محلی. خود تکلیف پیچیده نیست. آنچه پیچیده است این است که چگونه ایجنت را مجبور کنید تا آن را تکمیل کند.

آن را دو بار اجرا می‌کنید. بار اول: فقط پرامپت، بدون آماده‌سازی. بار دوم: هارنس کمینه (مثلاً `AGENTS.md`، `init.sh`، `feature_list.json`) از قبل در ریپازیتوری قرار داده شده. سپس مقایسه کنید.

این سناریو دوره از یک بازه‌ی بازاب/آماده‌سازی کوتاه به عنوان نمونه استفاده می‌کند، نه یک نتیجه‌ی اندازه‌گیری شده‌ی ثابت.

## استفاده از پروژه‌ی بررسی شده

مسیر ریپازیتوری: [`projects/project-01/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-01)

| دایرکتوری | محتوای آن | چگونه از آن استفاده کنید |
|------|------|------|
| [`starter/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-01/starter) | اجرای هارنس ضعیف. تنها [`task-prompt.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-01/starter/task-prompt.md) به عنوان توضیح تکلیف و بدون `AGENTS.md` یا `feature_list.json` دارد. توجه: `starter/` همچنین شامل یک پیاده‌سازی مرجع برنامه است — کد برنامه (`src/`، `package.json`، configs، `scripts/`) را قبل از اجرا حذف کنید تا ایجنت آن را از صفر بسازد. سند‌های نمونه `data/` انتخاب شما است: آن‌ها را در هر دو اجرا نگاه دارید یا از هر دو حذف کنید تا دو اجرا متقارن بمانند. | پرامپت را به ایجنت کدنویسی خود بدهید و اندازه‌گیری کنید که چه تکمیل می‌کند بدون ساختار اضافی. |
| [`solution/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-01/solution) | همان بخش محصول با artefact‌های هارنس صریح: [`AGENTS.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-01/solution/AGENTS.md)، [`CLAUDE.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-01/solution/CLAUDE.md)، [`init.sh`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-01/solution/init.sh)، [`feature_list.json`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-01/solution/feature_list.json)، [`claude-progress.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-01/solution/claude-progress.md)، و [`docs/`](https://github.com/walkinglabs/learn-harness-engineering/tree/main/projects/project-01/solution/docs) ([`ARCHITECTURE.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-01/solution/docs/ARCHITECTURE.md)، [`PRODUCT.md`](https://github.com/walkinglabs/learn-harness-engineering/blob/main/projects/project-01/solution/docs/PRODUCT.md)). | مقایسه کنید که چگونه همان تکلیف از طریق قوانین و مدارک راستی‌آزمایی مشخص می‌شود. قبل از اجرای قوی، مدارک بررسی شده را reset کنید: هر status `feature_list.json` را به `not-started` تنظیم کنید و `evidence`/`testedAt` آن را پاک کنید (فیلد‌ها را نگاه دارید)، و سابقه‌ی جلسه در `claude-progress.md` را پاک کنید (عنوان را نگاه دارید)، وگرنه ایجنت هر چهار قابلیت را در حال حاضر passing می‌بیند و چیزی برای ساختن ندارد. |

چهار قابلیت‌های مشخص عبارت‌اند از: راه‌اندازی پنجره، فهرست سند، پنل سوال، و ایجاد دایرکتوری داده‌های محلی. `solution/feature_list.json` را برای مدارک مورد انتظار هر قابلیت بررسی کنید.

## ابزارها

- Claude Code یا Codex (یکی را انتخاب کنید، هر دو اجرا را از آن استفاده کنید)
- دو دایرکتوری کاری منزوی (یکی در هر اجرا؛ هیچ‌گاه هر دو در حالی که اجرا فعال است موجود نباشند)
- Node.js + Electron (stack پروژه)
- تایمر (مدت زمان هر اجرا را ثبت کنید)

## مکانیسم هارنس

هارنس کمینه: `AGENTS.md` + `init.sh` + `feature_list.json` + `CLAUDE.md` + `claude-progress.md` + `docs/`

## پروتکل اجرا

### آماده‌سازی

۱. دو دایرکتوری کاری منزوی آماده کنید، برای مثال `p01-baseline/` و `p01-improved/`. یکی را در یک زمان اجرا کنید: فایل‌ها را تنظیم کنید، اجرا کنید، نتایج را بایگانی کنید، دایرکتوری را حذف کنید، سپس دیگری را شروع کنید.
۲. از شاخه‌های git برای جدا کردن دو اجرا استفاده نکنید. ایجنت کدنویسی دسترسی کامل فایل‌سیستم دارد و دایرکتوری‌های خواهر و برادر و branch refs را بررسی می‌کند؛ اگر اجرای ضعیف بتواند فایل‌های هارنس قوی (`feature_list.json`، `claude-progress.md`، `docs/`) را ببیند، آزمایش آلوده است.
۳. پرامپت تکلیف یکسانی را برای هر دو اجرا آماده کنید، متن از `starter/task-prompt.md`: "یک برنامه‌ی Electron بسازید که می‌تواند اسناد را نشان دهد و به سوالات پاسخ دهد."

### اجرای اول (هارنس ضعیف)

در `p01-baseline/`، تنها پرامپت تکلیف را قرار دهید (بدون فایل‌های هارنس).

۱. ایجنت را تنها با پرامپت بالا شروع کنید.
۲. `AGENTS.md` ندهید، اسکریپت initialization ندهید، معیار قبول ندهید.
۳. هنگامی که ایجنت متوقف می‌شود، `npm start` را اجرا کنید (یا هر فرمان راه‌اندازی که تولید کرد) تا بررسی کنید که برنامه راه‌اندازی شود.
۴. ثبت کنید: output terminal، diff کلیدی، خلاصه‌ی نهایی ایجنت.
۵. **کد را به صورت دستی اصلاح نکنید.** اگر راه‌اندازی نشد، آن را به عنوان آن ثبت کنید.
۶. نتایج را بایگانی کنید، `p01-baseline/` را حذف کنید، سپس تست دوم را اجرا کنید.

### اجرای دوم (هارنس قوی)

در `p01-improved/`، قبل از شروع ایجنت، آماده کنید:

- `AGENTS.md`: ساختار پروژه، دستورات راه‌اندازی، قوانین مرز لایه Electron
- `CLAUDE.md`: مرجع سریع برای ایجنت (فرمان‌های ساخت/اجرا، فایل‌های کلیدی)
- `init.sh`: تأیید اینکه پروژه به صورت تمیز ساخته می‌شود (`npm install && npm run check && npm run build`)
- `feature_list.json`: چهار قابلیت و status تکمیل آن‌ها
- `claude-progress.md`: سابقه‌ی پیشرفت و مدارک
- `docs/`: مشخصات معماری و محصول که `AGENTS.md` به ایجنت می‌گوید ابتدا آن را بخواند (`ARCHITECTURE.md`، `PRODUCT.md`)

سپس مدارک بررسی شده را reset کنید: هر status `feature_list.json` را به `not-started` تنظیم کنید و `evidence`/`testedAt` آن را پاک کنید (فیلد‌ها را نگاه دارید)، و سابقه‌ی جلسه در `claude-progress.md` را پاک کنید (عنوان را نگاه دارید). ایجنت را با همان پرامپت اجرای اول شروع کنید. هنگامی که متوقف می‌شود، `./init.sh` را اجرا کنید و نتیجه را ثبت کنید.

## چگونه نتایج را اندازه‌گیری کنید

| شاخص | توضیح |
|------|------|
| Completion | کامل / جزئی / ناموفق |
| اولین راه‌اندازی موفق | زمان از شروع تا اولین `npm start` موفق (یا فرمان راه‌اندازی که تولید کرد) |
| Retries | چند مداخله‌ی انسانی برای راه‌اندازی موفق لازم بود |
| موارد گمشده | کدام قابلیت‌ها هنوز هم وقتی ایجنت تکمیل را اعلام کرد اجرا نشدند |
| متوقف زودرس | آیا ایجنت تکمیل را اعلام کرد در حالی که برنامه هنوز نمی‌توانست اجرا شود |

## برای ارسال چه کاری

- ثبت اجرای هارنس ضعیف: پرامپت، سابقه‌ها/transcript، diff نهایی، مدارک راه‌اندازی
- ثبت اجرای هارنس قوی: یکی، به علاوه فایل‌های هارنسی که آماده کردید
- یک یادداشت مقایسه (۱-۲ صفحه): آنچه متفاوت بود، داده‌ها، نتیجه‌گیری شما

## فریم‌بندی تجربی

این آزمایش مقایسه است، نه نیازی که هر دو اجرای ایجنت یک برنامه‌ی Electron آماده‌ی تولید تولید کند. همان تکلیف را در برابر `starter/` ضعیف و `solution/` هارنس صریح اجرا کنید، سپس ثبت کنید کدام قابلیت‌ها هر اجرا تکمیل می‌کند و چه مدارکی از نتیجه پشتیبانی می‌کند. output جزئی یا شکسته مدارک تجربی معتبر است؛ فهرست قابلیت‌ها آنچه را که باید اندازه‌گیری شود تعریف می‌کند، نه نیاز اینکه اجرای فقط پرامپت باید هر موارد را پاس کند.

## سخنرانی‌های مرتبط

- [سخنرانی ۰۱. مدل‌های قوی به معنای اجرای قابل‌اعتماد نیست](./../../lectures/lecture-01-why-capable-agents-still-fail/index.md)
- [سخنرانی ۰۲. هارنس واقعاً چیست](./../../lectures/lecture-02-what-a-harness-actually-is/index.md)
- [سخنرانی ۰۶. ایجنت را قبل از هر جلسه کار Initialization کنید](./../../lectures/lecture-06-why-initialization-needs-its-own-phase/index.md)
