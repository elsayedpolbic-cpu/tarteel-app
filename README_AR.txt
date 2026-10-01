ترتيل PWA — نسخة تثبيت على الهاتف
================================

هذه الحزمة لا تغيّر قاعدة البيانات ولا الحسابات.
هي غلاف PWA لتطبيق ترتيل الحالي:
https://script.google.com/macros/s/AKfycbzPaxl3n-ZlF0pQxYiFEvvLNxLv3gW9sQYgYWSTSYk_d4b200FbEmr_EojxFIizzQi6fA/exec

الخطوة 1 — Apps Script
-----------------------
استبدل دالة doGet فقط بالموجود في:
DOGET_REPLACEMENT.txt

ثم:
Deploy > Manage deployments > Edit > New version > Deploy

الهدف من ALLOWALL هنا هو السماح لنسخة الـPWA بعرض تطبيق Apps Script داخل نافذة التطبيق.

الخطوة 2 — إصلاح كروت الموبايل
-------------------------------
افتح Styles.html الحالي.
قبل آخر </style> مباشرة الصق محتوى:
MOBILE_FIX_APPEND.txt

ثم اعمل Deploy لنسخة جديدة.

الخطوة 3 — نشر الـPWA
---------------------
أنشئ Repository جديد في GitHub، وارفع محتويات هذا المجلد إلى الجذر:
- index.html
- manifest.webmanifest
- sw.js
- favicon.svg
- .nojekyll
- مجلد icons

ثم:
GitHub > Repository > Settings > Pages
Build and deployment:
Deploy from a branch
Branch: main
Folder: /(root)
Save

انتظر حتى يظهر رابط GitHub Pages.

الخطوة 4 — التثبيت على Android
-------------------------------
افتح رابط GitHub Pages في Chrome.
ثم:
⋮ > Install app
أو:
⋮ > Add to Home screen

بعد التثبيت سيظهر "ترتيل" في قائمة التطبيقات ويفتح Standalone بدون شريط Chrome.

مهم
----
- لا تستخدم رابط Apps Script مباشرة كاختصار إذا كنت تريد شكل App كامل.
- الـPWA يحتاج إنترنت لتشغيل بيانات ترتيل لأن قاعدة البيانات على Google Apps Script.
- شاشة الـPWA نفسها يمكن أن تفتح Offline، لكن بيانات الأعمال لن تعمل بدون إنترنت.
