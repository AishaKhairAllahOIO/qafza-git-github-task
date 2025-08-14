1. إنشاء SSH Key وربطه بحساب GitHub
-إنشاء المفتاح:
ننفذ الأمر التالي:
ssh-keygen -t ed25519 -C "aishakhairallah3.com"
نستخدم المسار الافتراضي بالضغط على Enter.
ندخل كلمة مرور
نضيف المفتاح إلى ssh agent عن طريق الأمر:
ssh-add ~/.ssh/id_ed25519
ننسخ المفتاح العام  بعد تنفيذ الأمر التالي الذي يقوم بعرضه:
cat ~/.ssh/id_ed25519.pub

-ربط المفتاح  بحساب GitHub:
انتقل إلى GitHub → Settings → SSH and GPG keys → New SSH key
نلصق المفتاح العام في مكانه  ونضغط Add SSH key
 
-اختبار الاتصال
ssh -T git@github.com
تظهر الرسالة:
Hi <AishaKhairAllahOIO>! You've successfully authenticated, but GitHub does not provide shell access

2. إنشاء Repository:
فتح terminator لمستخدمي linux 
الانتقال إلى الDesktop عن طريق الأمر 
cd Desktop
إنشاء directory عن طريق الأمر mkdir qafza-git-github-task
الانتقال الى المجلد عن طريق الأمر cd qafza-git-github-task
تنفيذ الأمر : git init ليصبح الrepo محلي 
إنشاء بيئة افتراضية عن طريق الأمر:
python3 -m venv venv  لمنع حدوث conflect بنسخ المكتبات المستخدمة في المشاريع بحيث نستطيع تجاهل الglobal env، واستخدامها عند تفعيلها بأمر:
source venv\bin\activate 
إنشاء ملف .gitignore عن طريق الأمر nano .gitignore الذي يفتح محرر الnano, نضيف الملفات التي نريد تجاهلها مثل البيئة الافتراضية والملفات ذات الحجم الكبير والبيئة الافتراضية والتي تحوي على مفاتيح ومعلومات سرية...
إنشاء ملف README.md عن طريق الأمر  nano README.md وبداخله كتبت خطوات تنفيذ التاسك كما هو مطلوب 
إنشاء ملف بايثون nano task.py وكتابة سطر برمجي بداخله وحفظه
الآن نستطيع أن ننتقل إلى مرحلة الstaging ثم رفعها على الريموت 
git add .
git commit -m "something"
git branch -M main لتغيير اسم الbranch منmaster إلى main
git remote add origin git@github.com:AishaKhairAllahOIO/qafza-git-github-task.git
git push -u origin main 
الآن أصبح الريبو على الريموت، نستطيع إضافة أي شيء للملفات ورفعها للريموت الآن 

تمّ بعون الله.
