---
title: "ساخت سایت استاتیک با Hugo"
description: 
date: 2025-12-16T11:43:23+03:30
image: 
math: 
license: 
hidden: false
comments: true
draft: false
categories: ["آموزشی","hugo"]
tags: ["hugo", "آموزشی", "web", "سایتـاستاتیک"]
---

# مقدمه
خوب همونطور که قرار شد یه آموزش برای ساخت یه سایت استاتیک با استفاده از [Hugo](https://gohugo.io/) و استقرار اون روی [صفحات گیت‌هاب](https://pages.github.com/) رو براتون آماده کردم. با هر تغییری که روی سایت خودم میدم این پست رو آپدیت می‌کنم و امکانات جدیدی که خودم ازشون استفاده می‌کنم رو به این پست اضافه خواهم کرد.

# تفاوت سایت ایستا و پویا 
اولین چیزی که باید راجع بهش صحبت کنیم، اینه که شما نیاز به یه سایت استاتیک (ایستا) دارید و یا باید یک سایت داینامیک (پویا) داشته باشید. سایت ایستا مجموعه‌ای از فایل‌های `html` ،`css` یا جاوا اسکریپته که همون طوری که کد نویسی شده، به کاربر نمایش داده می‌شه و هر تغییری، فقط با تغییر کدهای سایت به کاربر نشون داده میشه. اما در عوض سایت پویا سایتیه که محتواش بدون نیاز به ویرایش کدها، به صورت تعاملی به کاربر نشون داده میشه و قابل تغییره. خوب حالا بیاین این دو مدل از سایت رو با هم مقایسه کنیم.

سایت‌های استاتیک سرعت بسیار بالایی دارند و هزینه بسیار کمی برای توسعه و راه‌اندازی اون‌ها مورد نیازه اما در عوض محتواشون ثابته و قابلیت‌های بسیار محدودی دارند و زمانی که حجم سایت زیاد می‌شه مدیریت سایت بسیار دشوار می‌شه. 

سایت‌های داینامیک محتوای پویایی دارند. میتونن با کاربر تعامل کنند و مدیریت محتوا در این سایت‌ها بسیار راحته و قابلیت‌های پیشرفته‌ای دارند، اما در عوض سرعت کمتر توسعه پیچیده‌تر و هزینه بسیار بیشتری برای راه‌اندازی و نگهداری دارند. 

## کدام را انتخاب کنم 
اگه شما یک بلاگرید یا نیاز به یه سایت شخصی کوچیک دارید یا یه سایت آموزشی کوچیک می‌خواین بسازین بهتره که از سایت ایستا استفاده کنید، اما اگر قراره که یک کار بزرگ انجام بدین یا یه کار تجاری یا یه چیزی مثل یک فروشگاه حتماً باید سراغ سایت‌های داینامیک برید.

 

# راه‌اندازی سایت استاتیک با `Hugo` و `GitHub Pages`

## معرفی
`Hugo` یک فریم‌ورک سریع و مدرن برای ساخت سایت‌های استاتیک است که با زبان `Go` نوشته شده. `GitHub Pages` یک سرویس میزبانی رایگان برای سایت‌های استاتیک است. ترکیب این دو، راه‌حلی ایده‌آل برای ایجاد وبلاگ، مستندات یا وبسایت شخصی ارائه می‌دهد.

## مزایا
- **سرعت بالا**: سایت‌های استاتیک `Hugo` بسیار سریع بارگذاری می‌شوند
- **امنیت**: بدون پایگاه داده یا کد `backend`، آسیب‌پذیری کاهش می‌یابد
- **رایگان**: `GitHub Pages` به صورت رایگان سرویس میزبانی ارائه می‌دهد
- **مدیریت آسان**: با `Git` می‌توانید تاریخچه کامل تغییرات را داشته باشید
- **قالب‌های متنوع**: صدها قالب رایگان برای `Hugo` موجود است

## پیش‌نیازها
1. نصب `Git` ([دانلود](https://git-scm.com/))
2. حساب کاربری `GitHub` ([ثبت‌نام](https://github.com/))
3. نصب `Hugo` ([راهنمای نصب](https://gohugo.io/getting-started/installing/))

## مراحل راه‌اندازی
### ۱. نصب `Hugo`
برای نصب `Hugo` به این [آدرس](https://gohugo.io/installation/) برید و بسته به نوع سیستم عامل خودتون نصبش کنید.
من از آرچ لینوکس استفاده می‌کنم.پس با `pacman` نصبش می‌کنم:

{{< codefile file="bash" lang="bash" lines="false" >}}
sudo pacman -S hugo
{{< /codefile >}}

### ۲. ایجاد پروژه جدید Hugo
حالا ترمینال رو باز کنید و به آدرسی برید که می‌خواهید سایتتون اونجا ساخته بشه و 

{{< codefile file="bash" lang="bash" lines="false" >}}
hugo new site نام-سایت-شما
cd نام-سایت-شما
{{< /codefile >}}

تمام. حالا شما یک سایت ایستا دارید. 

### ۳. اضافه کردن قالب
به سایت [Hugo Themes](https://themes.gohugo.io/) برید و یه قالب برای سایتتون انتخاب کنید. حواستون باشه که یه قالب چنذزبانه انتخاب کنید. من قالب [stack](https://github.com/CaiJimmy/hugo-theme-stack) رو انتخاب کردم.

برای نصب `stack` بهترین کار اینه که از تمپلیت آماده‌ای که برامون گذاشته استفاده کنیم. به این [آدرس](https://github.com/CaiJimmy/hugo-theme-stack-starter) برید و روی `Use this template` کلیک کنید.
![create-repo-from-template](https://user-images.githubusercontent.com/5889006/156916624-20b2a784-f3a9-4718-aa5f-ce2a436b241f.png)
حالا Create new reposity رو انتخاب کنید.

در پنجره‌ای که براتون باز می‌شه در قسمت `Repository name` نام مخزن جدید که همون سایتتونه رو انتخاب کنید. فرمت نام باید به این شکل باشه:

{{< codefile file="" lang="" lines="false" >}}
username.github.io
{{< /codefile >}}
که username همون نام کاربری گیت‌هابتونه.

حالا `create repository` رو بزنید. کار تمامه و سایت شما با قالب `stack` روی گیت‌هاب سوار شده. فقط یک مرحله‌ی دیگه مونده و اونم اینه که به قسمت تنظیمات مخزن ساخته شده برید و `Pages` رو انتخاب کنید. حالا `Build branch` رو از `master` به `gh-pages` تغییر بدید.
![change-build-branch](https://private-user-images.githubusercontent.com/16586200/298284692-12c763cd-bead-4923-b610-8788f388fcb5.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjU5MTIzMjcsIm5iZiI6MTc2NTkxMjAyNywicGF0aCI6Ii8xNjU4NjIwMC8yOTgyODQ2OTItMTJjNzYzY2QtYmVhZC00OTIzLWI2MTAtODc4OGYzODhmY2I1LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNTEyMTYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjUxMjE2VDE5MDcwN1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWRlMmJmYmIyM2FkZTE5OWU2NDNhNDRhNDU5ZDM5M2RmM2JiYTIzOWJmOWZkMWNkM2I4ZTY5MWRkZjk3Yjg1YWQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.PQGXP8dMQPOwGP4NzftOSNPP8FRmZ_2z1b_2waQXWqw)

خب کار ما تمامه و دیگه اینجا کاری نداریم.

### ۴. ساخت یک کلون از سایت روی سیستم محلی
تبریک میگم:) تا اینجای کار رو خوب پیش اومدید. بیاین یک کلون از سایتمون روی سیستممون درست کنیم.

ترمینال رو باز کنید و این دستور رو وارد کنید.

{{< codefile file="bash" lang="bash" lines="false" >}}
git clone https://github.com/username/username.github.io.git
{{< /codefile >}}

نام کاربری خودتون رو به جای `username` بذارید. فرض کنید قراره سایت منو کلون کنید:

{{< codefile file="bash" lang="bash" lines="false" >}}
git clone https://github.com/silvergit/silvergit.github.io.git
{{< /codefile >}}

حالا به پوشه سایت برید:

{{< codefile file="bash" lang="bash" lines="false" >}}
cd silvergit.github.io
{{< /codefile >}}


و `Hugo` رو اجرا کنید:

{{< codefile file="bash" lang="bash" lines="false" >}}
Hugo server -D
{{< /codefile >}}

خروجی لینکی رو به شما می‌ده که میتونید خروجی سایتتون به صورت لوکال یا محلی رو توی اون آدرس ببینید

{{< codefile file="bash" lang="bash" lines="false" >}}
Built in 133 ms
Environment: "development"
Serving pages from disk
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1) 
Press Ctrl+C to stop
{{< /codefile >}}

برای من اینه: `http://localhost:1313/`

### ۵. اولین پست سایت

بریم سراغ ساخت یه صفحه جدید. برای این کار این دستور رو وارد کنید:

{{< codefile file="" lang="bash" lines="false" >}}
hugo new content posts/hello.md
{{< /codefile >}}
در پوشه `content` یک فایل مارک داون جدید براتون ساخته می‌شه.

{{< alert type="tip" title="نکته" >}}
 از یک ویرایشگر برای نوشتن فایل‌های `markdown` مثل `vscode` استفاده کنید.{{< /alert >}}

این متن را در فایل کپی کنید:

{{< codefile file="hello.md" lang="markdown" lines="false" >}}
---
title: "سلام دنیا"
description: "اولین پست سایت"
date: 2025-12-12T12:53:03+03:30
image: 
math: 
license: 
hidden: false
comments: true
draft: false
categories: ["عمومی"]
tags: []
---

این اولین پست من توی این سایته.
{{< /codefile >}}


قسمت بالای فایل رو `Hugo` میخونه و تصمیم می‌گیره که با فایل چی‌کار کنه. مثلا تاریخ ساخت فایل کی بوده یا عنوان صفحه چیه و یا اینکه برای این صفحه چه تگ‌هایی رو باید معرفی کنه.

خط آخر هم همون چیزیه که قراره توی پست اولتون ببینید. فایل رو ببنددید و دوباره `Hugo` رو اجرا کنید.

{{< codefile file="" lang="bash" lines="false" >}}
hugo server -D
{{< /codefile >}}

### ۶. پیکربندی فایل `config.toml`
فایل پیکربندی معمولا در ریشه پروژه وجود داره اما بعضی وقت‌ها هم توی پوشه `config` یا `config/_default` می‌تونید پیداش کنید.

یه نمونه ساده از کانفیگ رو میتونید ببینید:
{{< codefile file="config.toml" lang="toml" lines="false" >}}
baseURL = "https://username.github.io/"
languageCode = "fa-ir"
title = "عنوان سایت شما"
theme = "ananke"

[params]
  description = "توضیحات سایت شما"
{{< /codefile >}}

کانفیگ من این شکلیه:
{{< codefile file="config.toml" lang="toml" lines="false" >}}
# Change baseurl before deploy
baseurl = "https://silvergit.github.io/"
languageCode = "en-us"
title = "Morface"

# Theme i18n support
# Available values: en, fr, id, ja, ko, pt-br, zh-cn, zh-tw, es, de, nl, it, th, el, uk, ar
defaultContentLanguage = "fa"

# Set hasCJKLanguage to true if DefaultContentLanguage is in [zh-cn ja ko]
# This will make .Summary and .WordCount behave correctly for CJK languages.
hasCJKLanguage = false

# Change it to your Disqus shortname before using
disqusShortname = "hugo-theme-stack"

[pagination]
pagerSize = 5
{{< /codefile >}}

کل کانفیگ سایت من توی فایل‌های جداگانه ساخته می‌شه:
{{< codefile file="" lang="bash" lines="false" >}}
config
└── _default
    ├── config.toml
    ├── languages.toml
    ├── markup.toml
    ├── menu.toml
    ├── module.toml
    ├── params.toml
    ├── permalinks.toml
    └── related.toml
{{< /codefile >}}

{{< alert type="tip" title="نکته" >}}
شما میتونید فقط از یک فایل استفاده کنید و تمام این تنظیمات رو فقط در فایل `config.toml` کپی کنید.{{< /alert >}}

برای دو زبانه‌کردن سایت من از فایل `languages.toml` استفاده میکنم:
{{< codefile file="languages.toml" lang="toml" lines="false" >}}
[fa]
languageName = "فارسی"
languagedirection = "rtl"
title = "مورفیس"
weight = 1
[en]
languageName = "English"
languagedirection = "ltr"
title = "morface"
weight = 2
{{< /codefile >}}

### ۷. آپلود تغییرات روی گیت‌هاب
{{< codefile lang="bash" lines="false" >}}
cd public
git init
git add .
git commit -m "اولین انتشار"
git branch -M main
git remote add origin https://github.com/username/username.github.io.git
git push -u origin main
{{< /codefile >}}


## نکات مهم

### دامنه سفارشی
اگر می‌خواهید از دامنه شخصی استفاده کنید:
1. فایل `CNAME` را در پوشه `static` ایجاد کنید
2. نام دامنه خود را در آن وارد کنید
3. `DNS` خود را مطابق راهنمای `GitHub Pages` تنظیم کنید

### بهینه‌سازی برای موتورهای جستجو
- از قالب‌های `SEO-Friendly` استفاده کنید
- متا تگ‌ها را به درستی تنظیم کنید
- ساختار `URL` را خوانا انتخاب کنید

### پشتیبانی از زبان فارسی
- در `config.toml` مقدار `languageCode` را `fa-ir` تنظیم کنید
- از قالب‌هایی با پشتیبانی `RTL` استفاده کنید
- فونت‌های فارسی مناسب اضافه کنید

## منابع مفید
- [مستندات رسمی Hugo](https://gohugo.io/documentation/)
- [راهنمای GitHub Pages](https://docs.github.com/pages)
- [گالری قالب‌های Hugo](https://themes.gohugo.io/)
- [راهنمای Markdown](https://www.markdownguide.org/)

## نتیجه‌گیری
با استفاده از `Hugo` و `GitHub Pages` می‌توانید در کمترین زمان و بدون هزینه، یک سایت استاتیک حرفه‌ای راه‌اندازی کنید. این روش برای وبلاگ‌نویسان، توسعه‌دهندگان و کسب‌وکارهای کوچک ایده‌آل است.