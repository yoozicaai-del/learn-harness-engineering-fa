[نسخه‌ی انگلیسی ←](../../../en/resources/reference/index.md)

# مرجع

این یادداشت‌ها نحوه استفاده از الگوها را به عنوان یک هارنس کاری توضیح می‌دهند، نه یک مجموعه‌ی سست از فایل‌ها.

## یادداشت‌های مرجع داخلی

- [`method-map.md`](./method-map.md): نقشه‌برداری حالت‌های شکست رایج طولانی‌مدت به عامل یا خط‌مشی‌ای که آن را اول رفع می‌کند
- [`initializer-agent-playbook.md`](./initializer-agent-playbook.md): آنچه آماده‌کننده باید قبل از شروع کار ویژگی جا بگذارد
- [`coding-agent-startup-flow.md`](./coding-agent-startup-flow.md): جریان شروع جلسه ثابت برای اجرای کدگذاری بعدی
- [`prompt-calibration.md`](./prompt-calibration.md): نحوه نگاه‌داری دستورات ریشه‌ای تیز بدون کثیف و شکننده کردن آن‌ها

## مقالات اصلی

این فهرست عمداً محدود است. هارنس بدان معناست سیستم اجرایی دور مدل: حلقه‌ی عامل، اجرای ابزار، جداسازی شرطی، وضعیت، متن، راستی‌آزمایی، پایان‌دهی، تنظیم پویا، و رصدپذیری. مقالات کلی مهندسی پرامپت یا مقالات قاب عامل گسترده در فهرست اصلی جای ندارند.

سه مقاله اصلی باقی‌مانده ستون‌فقرات دوره را تشکیل می‌دهند:

- [OpenAI: مهندسی هارنس: استفاده از Codex در جهانی عامل‌محور](https://openai.com/index/harness-engineering/) (2026-02-11): ریپازیتوری‌های عامل‌محور، متن محلی ریپازیتوری، پیدایش‌دهی شخصی، و حفاظت ساختاری.
- [Anthropic: هارنس‌های موثر برای عوامل طولانی‌مدت](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) (2025-11-26): عامل آماده‌کننده، عامل کدگذاری، فهرست قابلیت‌ها، گزارش پیشرفت، و تحویل میان پنجره‌های متن.
- [Anthropic: طراحی هارنس برای توسعه‌ی برنامه‌ی طولانی‌مدت](https://www.anthropic.com/engineering/harness-design-long-running-apps) (2026-03-24): نقش‌های برنامه‌ریز / تولیدکننده / ارزیاب، بازنشانی‌های متن، ساده‌سازی هارنس، و فرض‌های کهنه.

تنها چند مقاله‌ی بسیار مرتبط 2026 اضافه می‌شوند:

- [OpenAI: بازگشایی حلقه‌ی عامل Codex](https://openai.com/index/unrolling-the-codex-agent-loop/) (2026-01-23): هارنس اجرایی Codex، فراخوانی ابزار، رشد متن، و پایان‌دهی حلقه.
- [Anthropic: رفع ابهام ارزیابی‌ها برای عوامل هوش مصنوعی](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) (2026-01-09): ارزیابی مدل و هارنس با هم، و تمایز هارنس ارزیابی از هارنس عامل.
- [LangChain: بهبود عوامل عمیق با مهندسی هارنس](https://www.langchain.com/blog/improving-deep-agents-with-harness-engineering) (2026-02-17): ثابت نگاه‌داری مدل در حالی که بهبود پرامپت‌های سیستم، ابزارها، middleware، ردیابی، و خود‌راستی‌آزمایی برای جابه‌جایی عامل کدگذاری از Top 30 به Top 5 در Terminal Bench 2.0.
- [Thoughtworks / Martin Fowler: مهندسی هارنس برای کاربران عامل کدگذاری](https://martinfowler.com/articles/harness-engineering.html) (2026-04-02): هارنس‌های کاربر عامل کدگذاری به عنوان راهنمای feedforward و حسگر بازخورد، با کنترل‌های قطعی و استنتاجی.
- [Cursor: بهبود مستمر هارنس عامل ما](https://cursor.com/blog/continually-improving-agent-harness) (2026-04-30): رفتار با هارنس به عنوان سیستم محصول بهبود یافته‌ی مستمر با ارزیابی‌های آفلاین، معیارهای آنلاین، تاکسونومی خطای ابزار، و تنظیم خاص مدل.

## منابع توسیع‌یافته 2026

اینها منابع دوره‌ی اصلی نیستند، اما هنگام طراحی ماژول‌های هارنس خاص مفید هستند. این بخش تنها منابعی را نگه می‌دارد که متن آن‌ها مستقیماً حلقه‌ی عامل، اجرای ابزار، مدیریت متن، راستی‌آزمایی، جداسازی شرطی، لایه‌های کنترل، یا مدیریت عدول را پوشش می‌دهد. محصولات عامل خالص، اعلانات پلتفرم، مطالعات موردی تیم، و معیارها حذف می‌شوند.

- [OpenAI: قفل زدایی هارنس Codex: نحوه‌ی ساخت App Server](https://openai.com/index/unlocking-the-codex-harness/) (2026-02-04): هارنس به عنوان پروتکل App Server قابل‌استفاده‌ی مجدد با چرخه‌ی ریسمان، از سر گرفتن، انشعاب، تفاوت‌ها، و ادغام کلاینت.
- [OpenAI Developers: اجرای وظایف افق طولانی با Codex](https://developers.openai.com/blog/run-long-horizon-tasks-with-codex) (2026-02-23): حافظه‌ی پروژه دوام‌آور، تصدیق سنگ‌راه، و نمونه‌های انجام شده برای وظایف طولانی‌مدت.
- [OpenAI: تحول بعدی SDK عوامل](https://openai.com/index/the-next-evolution-of-the-agents-sdk/) (2026-04-15): هارنس‌های بومی مدل، اجرای جداسازی شرطی، و اجرای فایل/فرمان.
- [OpenAI: مشخصات بازمتن برای تنظیم پویای Codex: Symphony](https://openai.com/index/open-source-codex-orchestration-symphony/) (2026-04-27): تبدیل تابلوی ردیاب مسائل یا Linear به صفحه‌ی کنترل عامل چندگانه.
- [Anthropic: ساخت کامپایلر C با تیمی از Claudeهای موازی](https://www.anthropic.com/engineering/building-c-compiler) (2026-02-05): تیم‌های عامل موازی، قفل‌های وظیفه، همگام‌سازی git، جداسازی کانتینر، و حلقه‌های خودمختار.
- [Anthropic: مقیاس‌گذاری عوامل مدیریت‌شده: جداسازی مغز از دست‌ها](https://www.anthropic.com/engineering/managed-agents) (2026-04-08): نمای meta-harness که جلسه، هارنس، و جداسازی شرطی را به عنوان رابط‌های قابل‌تعویض جدا می‌کند.
- [Anthropic: به‌روزرسانی درباره‌ی گزارش‌های کیفیت Claude Code اخیر](https://www.anthropic.com/engineering/april-23-postmortem) (2026-04-23): تلاش استدلال، کاهش متن، و پرامپت‌های سیستم به عنوان تغییرات هارنس که به مدیریت عدول احتیاج دارند.
- [LangChain: مدیریت متن برای عوامل عمیق](https://www.langchain.com/blog/context-management-for-deepagents) (2026-01-28): آفلود سیستم‌فایل، کوتاه‌سازی فراخوانی ابزار، خلاصه‌سازی، و ارزیابی‌های هدفمند برای هارنس‌های مدیریت متن.
- [LangChain: تنظیم عوامل عمیق برای کار خوب با مدل‌های مختلف](https://www.langchain.com/blog/tuning-deep-agents-different-models) (2026-04-29): پروفایل‌های هارنس خاص مدل برای پرامپت‌ها، نام‌های ابزار، middleware، و پیکربندی زیرعامل.
- [LangChain: یادگیری مستمر برای عوامل هوش مصنوعی](https://www.langchain.com/blog/continual-learning-for-ai-agents) (2026-04-05): تقسیم بهبود عامل به لایه‌های مدل، هارنس، و متن، تقویت‌شده توسط ردیابی.
- [Microsoft: هارنس عامل در Agent Framework](https://devblogs.microsoft.com/agent-framework/agent-harness-in-agent-framework/) (2026-03-12): هارنس‌های shell/سیستم‌فایل، جریان تصدیق، اجرای shell میزبان‌شده، و فشردن متن.
- [Google: اعلان ADK برای Java 1.0.0](https://developers.googleblog.com/announcing-adk-for-java-100-building-the-future-of-ai-agents-in-java/) (2026-03-30): پلاگین‌ها، فشردن رویداد، HITL، خدمات جلسه/حافظه، و A2A به عنوان بدوی‌های هارنس قابل‌استفاده‌ی مجدد.
- [GitHub: خودکار‌کردن وظایف ریپازیتوری با GitHub Agentic Workflows](https://github.blog/ai-and-ml/automate-repository-tasks-with-github-agentic-workflows/) (2026-02-13): GitHub Actions به عنوان اجرایی جریان کاری agentic با خروجی‌های ایمن، جداسازی شرطی، اجازه‌ها، و بررسی.
- [AWS: عوامل هوش مصنوعی در شرکت‌ها: بهترین روش‌ها با Amazon Bedrock AgentCore](https://aws.amazon.com/blogs/machine-learning/ai-agents-in-enterprises-best-practices-with-amazon-bedrock-agentcore/) (2026-02-03): لایه‌های هارنس شرکتی در سراسر Runtime، Memory، Gateway، Identity/Policy، Observability، و Evaluations.
- [Stripe: Minions: عوامل کدگذاری یک‌شلاقی، از سر تا پا Stripe](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents) (2026-02-09) و [قسمت 2](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents-part-2) (2026-02-19): جداسازی devbox، هارنس‌های عامل سفارشی، ماشین‌های حالت blueprint، فایل‌های قانون، مدیریت ابزار MCP، کنترل‌های امنیتی، و حلقه‌های بازخورد pre-push/CI.
- [Cognition: آنچه ما از ساخت عوامل ابری یاد گرفتیم](https://cognition.ai/blog/what-we-learned-building-cloud-agents) (2026-04-23): جداسازی VM، تصویر/ازسر گرفتن جلسه، تنظیم پویا، مدیریت، ردیابی حسابدهی، و ادغام‌ها برای اجرا‌های عامل ابری.
- [Cognition: عوامل چندگانه: آنچه واقعاً کار می‌کند](https://cognition.ai/blog/multi-agents-working) (2026-04-22): حلقه‌های تولیدکننده-تصدیق‌کننده، بررسی‌کنندگان متن پاک‌کردن متن، مسیریابی دوست هوشمند، هماهنگی مدیر-فرزند، و مرزهای ارتباطات میان‌عامل.
- [Addy Osmani: مهندسی حلقه](https://addyosmani.com/blog/loop-engineering/) (2026-06-07): قاب کار مهندسی حلقه‌ی کامل از `/goal` به شش بدوی — خودکارسازی، درخت کار، مهارت‌ها، اتصال‌دهنده، زیرعامل‌ها، وضعیت خارجی — به اضافه چهار هزینه خاموش.
- [Replit: راهنمایی تصمیم‌گیری: نگاه‌داری Replit Agent قابل‌اعتماد](https://blog.replit.com/decision-time-guidance) (2026-01-20، به‌روزرسانی 2026-01-23): طبقه‌بندی کم‌وزن راهنمایی موقعیتی کوتاهی را در نقطه تصمیم تزریق می‌کند به جای پر کردن تمام قوانین در پرامپت سیستم.
- [Vercel: نحوه‌ی تبدیل v0 به عامل کدگذاری موثر](https://vercel.com/blog/how-we-made-v0-an-effective-coding-agent) (2026-01-07): پرامپت‌های سیستم پویا، لایه‌ی بازنویسی جریان، و تصحیح‌کنندگان اتوماتیک قطعی/مدل‌محور.
- [Vercel: معرفی deepsec](https://vercel.com/blog/introducing-deepsec-find-and-fix-vulnerabilities-in-your-code-base) (2026-05-04): هارنس عامل کدگذاری متمرکز بر امنیت با مراحل اسکن، بررسی، تصدیق، غنی‌سازی، صادرات، پلاگین، و بررسی‌کننده امتناع.
- [Sourcegraph: CodeScaleBench](https://sourcegraph.com/blog/codescalebench-testing-coding-agents-on-large-codebases-and-multi-repo-software-engineering-tasks) (2026-03-03): مرجع هارنس eval/ابزار پوشش‌دهی پذیرش ابزار MCP، رونوشت استفاده ابزار، تضمین QA معیار، دروازه‌های تصدیق‌کننده/تکرارپذیری، و تکرار پرامپت/مقدمه.

منابع کلی منحصر به 2025 از فهرست اصلی حذف می‌شوند. مقاله‌ی هارنس Anthropic اصلی 2025 باقی می‌ماند زیرا منبع بنیادی برای دوره است.

## ترتیب خوانش پیشنهادی

1. `method-map.md`
2. `initializer-agent-playbook.md`
3. `coding-agent-startup-flow.md`
4. `prompt-calibration.md`
5. مهندسی هارنس OpenAI
6. هارنس‌های موثر Anthropic
7. طراحی هارنس برای توسعه‌ی برنامه‌ی طولانی‌مدت Anthropic
8. حلقه‌ی عامل Codex OpenAI
9. ارزیابی عامل Anthropic
10. بهبود عوامل عمیق LangChain
11. مهندسی هارنس برای کاربران عامل کدگذاری Thoughtworks / Martin Fowler
12. بهبود مستمر هارنس عامل ما Cursor
