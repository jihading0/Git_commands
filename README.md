# Git commands
شرح Git بشكل احترافي واقعي كما يُستخدم في الشركات (Production Workflow) بدون حشو—ركز لأن هذا هو الفرق بين مبتدئ ومطور يُوظَّف.

🧠 أولًا: كيف يُستخدم Git في سوق العمل (الصورة الكبيرة)

في الشركات، Git ليس مجرد أوامر… هو نظام إدارة إصدارات + تعاون + تتبع + أمان.

Workflow الحقيقي:
عندك Repository (مشروع)
تشتغل على Feature في Branch منفصل
تعمل Commit لكل تغيير منطقي
ترفع التعديلات (Push)
تعمل Pull Request
يتم Code Review
يتم دمج الكود (Merge)

👉 الهدف: منع كسر المشروع + تتبع كل تغيير + العمل الجماعي المنظم

⚙️ المرحلة 1: إعداد Git (مرة واحدة فقط)
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
تحقق:
git config --list

📌 في الشركات: يتم ربط Git مع حسابك على GitHub/GitLab.

📦 المرحلة 2: إنشاء وربط مشروع
إنشاء Repo جديد:
git init 
ربطه مع GitHub:
git remote add origin https://github.com/username/repo.git
جلب البيانات:
git clone <repo-url>

📌 في الشركات: غالبًا تستخدم clone وليس init.


📁 المرحلة 3: دورة العمل الأساسية (Core Workflow)
1. معرفة حالة المشروع
git status
2. إضافة الملفات (Stage)
git add file.js
git add .

📌 مهم:

add = تحضير التغييرات فقط
ليس حفظ نهائي
3. حفظ التغييرات (Commit)
git commit -m "Add login feature"

📌 في الشركات:

الرسالة يجب أن تكون واضحة:
❌ fix
✅ fix: resolve login validation bug
4. رفع التعديلات (Push)
git push origin main
5. سحب التحديثات (Pull)
git pull origin main

📌 مهم جدًا:

اسحب قبل أن تبدأ العمل لتجنب المشاكل
🌿 المرحلة 4: الـ Branching (أهم جزء في الشركات)
إنشاء Branch:
git branch feature-login
الانتقال:
git checkout feature-login

أو:

git switch feature-login
إنشاء + انتقال:
git checkout -b feature-login
الدمج (Merge):
git merge feature-login

📌 في الشركات:

يتم الدمج عبر Pull Request وليس يدويًا غالبًا
حذف Branch:
git branch -d feature-login
🔁 المرحلة 5: التعامل مع التحديثات والتعارضات
تحديث البيانات:
git fetch
إعادة ترتيب الكوميتات:
git rebase main

📌 الفرق:

merge = يحافظ على التاريخ
rebase = يجعل التاريخ نظيف (يستخدم كثيرًا في الشركات)
حل التعارضات:

عند حدوث Conflict:

افتح الملف
عدل الجزء المتعارض
ثم:
git add .
git commit
⏪ المرحلة 6: التراجع (Undo)
إلغاء staging:
git restore --staged file.js
تعديل آخر commit:
git commit --amend
الرجوع لحالة سابقة:
git checkout <commit-id>
حذف التغييرات:
git reset --hard

⚠️ خطير جدًا — يستخدم بحذر في الشركات

🔍 المرحلة 7: الاستكشاف والتتبع
عرض الكوميتات:
git log
بشكل مختصر:
git log --oneline
معرفة من عدل سطر:
git blame file.js

📌 تستخدم في:

Debugging
معرفة المسؤول عن الخطأ
🧪 المرحلة 8: أدوات احترافية تستخدم في الشركات
حفظ مؤقت (stash):
git stash
git stash pop

📌 يستخدم عندما:

تريد تبديل task بدون commit
العلامات (Tags):
git tag v1.0

📌 تستخدم في:

Releases
🏢 كيف تعمل فعليًا داخل شركة
السيناريو الواقعي:
git clone repo
git checkout -b feature-auth

# تشتغل
git add .
git commit -m "feat: implement login API"

git push origin feature-auth

ثم:

تفتح Pull Request
يتم مراجعة الكود
يتم الدمج في main
🧠 Best Practices (هذه ما يميز المحترف)
1. لا تعمل commit ضخم

✔️ اجعل كل commit له معنى

2. استخدم naming احترافي:
feature/login
fix/navbar-bug
hotfix/payment-error
3. اسحب دائمًا قبل الدفع:
git pull --rebase origin main
4. لا تعمل push مباشرة على main

🚫 خطأ مبتدئين

5. استخدم Conventional Commits:
feat:
fix:
refactor:
docs:
🚀 الخلاصة التنفيذية

لو أردت العمل مثل الشركات:

👉 ركز على:

Branching Strategy
Clean Commits
Pull Requests
Code Review
Rebase بدل merge العشوائي
🎯 لو تريد المستوى الاحترافي الحقيقي

أستطيع أن أعطيك:

🔥 Workflow شركات كاملة (GitFlow / Trunk-Based)
🔥 سيناريوهات مشاكل حقيقية وكيف تحلها
🔥 مشروع عملي تستخدم فيه Git كأنك داخل شركة

قل لي: عايز تتوظف بسرعة ولا تبقى Senior؟ وسأبني لك خطة تنفيذية مباشرة.
