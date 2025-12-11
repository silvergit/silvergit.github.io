
title: "آموزش کامل Hugo برای مبتدیان"
date: 2024-01-20
draft: false
description: "راهنمای گام به گام نصب و استفاده از Hugo"
categories: ["آموزش", "توسعه وب"]
tags: ["hugo", "آموزش", "توسعه وب"]

آموزش Hugo از صفر تا صد 📚
در این آموزش کامل، Hugo را از ابتدا یاد می‌گیریم.

فصل ۱: نصب Hugo
روی لینوکس
bash
# روش ۱: Snap
sudo snap install hugo --channel=extended

# روش ۲: دستی
wget https://github.com/gohugoio/hugo/releases/download/v0.125.5/hugo_extended_0.125.5_linux-amd64.tar.gz
tar -xvzf hugo_extended_0.125.5_linux-amd64.tar.gz
sudo mv hugo /usr/local/bin/
روی ویندوز
powershell
choco install hugo-extended
روی مک
bash
brew install hugo
فصل ۲: ایجاد اولین سایت
bash
# ایجاد پروژه جدید
hugo new site mysite
cd mysite

# اضافه کردن قالب
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke

# پیکربندی
echo 'theme = "ananke"' >> hugo.toml

# اجرای سرور
hugo server -D
فصل ۳: ساختار پروژه
text
mysite/
├── archetypes/       # قالب‌های محتوا
├── content/          # محتوای سایت
├── layouts/          # قالب‌های HTML
├── static/           # فایل‌های استاتیک
├── themes/           # تم‌ها
└── hugo.toml         # فایل پیکربندی
فصل ۴: ایجاد محتوا
ایجاد صفحه
bash
hugo new about.md
ایجاد پست وبلاگ
bash
hugo new posts/my-first-post.md
فصل ۵: پیکربندی پیشرفته
چندزبانه
toml
[languages]
  [languages.fa]
    languageName = "فارسی"
    weight = 1
    
  [languages.en]
    languageName = "English"
    weight = 2
منو
toml
[[menu.main]]
  name = "خانه"
  url = "/"
  weight = 1
فصل ۶: دیپلوی
GitHub Pages
bash
# ساخت سایت
hugo

# آپلود به GitHub
cd public
git init
git add .
git commit -m "Deploy site"
git branch -M main
git remote add origin https://github.com/username/repo.git
git push -u origin main
نتیجه
Hugo ابزار قدرتمندی است که یادگیری آن ارزش وقت گذاشتن دارد.

سطح: مبتدی
زمان مطالعه: ۲۰ دقیقه
پیش‌نیاز: آشنایی با ترمینال
