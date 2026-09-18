# ٹول کِٹ — PWA سے APK بنانے کا طریقہ

اس فولڈر میں آپ کی ویب ایپ کو PWA (Progressive Web App) بنانے کے لیے تمام ضروری فائلیں موجود ہیں:

```
index.html          ← مرکزی ایپ (manifest اور service worker کے ساتھ)
manifest.json        ← ایپ کی معلومات (نام، آئیکن، رنگ وغیرہ)
service-worker.js    ← آف لائن سپورٹ کے لیے
icons/
  icon-192.png
  icon-512.png
  icon-192-maskable.png
  icon-512-maskable.png
```

## مرحلہ 1: GitHub پر اپلوڈ کریں

1. GitHub پر ایک نیا ریپازیٹری (repository) بنائیں، مثلاً `toolkit-pwa`
2. اس فولڈر کی تمام فائلیں (structure کو ویسے ہی رکھتے ہوئے) ریپازیٹری میں اپلوڈ کریں
   - یقینی بنائیں کہ `icons` فولڈر اسی نام سے اندر موجود ہو

## مرحلہ 2: GitHub Pages فعال کریں

1. ریپازیٹری میں جائیں → **Settings** → **Pages**
2. "Source" میں **Deploy from a branch** منتخب کریں
3. Branch: `main` اور Folder: `/ (root)` منتخب کر کے **Save** کریں
4. چند منٹ بعد آپ کو ایک لنک ملے گا، جیسے:
   `https://your-username.github.io/toolkit-pwa/`
5. یہ لنک کھول کر چیک کریں کہ ایپ صحیح طرح لوڈ ہو رہی ہے

## مرحلہ 3: PWA Builder سے APK بنائیں

1. جائیں: **https://www.pwabuilder.com/**
2. اوپر باکس میں اپنا GitHub Pages لنک پیسٹ کریں (مثلاً `https://your-username.github.io/toolkit-pwa/`)
3. **Start** پر کلک کریں — یہ آپ کے manifest اور service worker کو خودکار چیک کرے گا
4. اسکور دیکھنے کے بعد **"Package For Stores"** پر کلک کریں
5. **Android** منتخب کریں
6. تفصیلات (Package ID، App name وغیرہ) دیکھ/بدل لیں — یہ خودکار manifest سے آ جائیں گی
7. **Generate** پر کلک کریں — یہ آپ کو `.apk` یا `.aab` فائل download کے لیے دے گا

## نوٹس

- یہ ایپ کچھ آن لائن لائبریریز استعمال کرتی ہے (Google Fonts، QR کوڈ جنریٹر، ZIP لائبریری) — پہلی بار انٹرنیٹ کے ساتھ کھولنے پر یہ کیش ہو جاتی ہیں، اس کے بعد آف لائن بھی چل سکتی ہے۔
- اگر آئیکن یا نام بدلنا ہو تو `manifest.json` میں ترمیم کریں۔
- APK بنانے کے بعد اسے کسی Android ڈیوائس پر انسٹال کر کے ٹیسٹ ضرور کریں۔
