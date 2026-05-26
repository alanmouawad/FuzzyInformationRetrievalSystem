# Fuzzy Information Retrieval System
An Arabic Information Retrieval desktop app in C# using Fuzzy Logic to rank Word documents on marketing. It features an Arabic stemmer, custom Stop Words filtering (e.g., prepositions), and a smart caching system for instant re-search results. Files are ranked based on title match, term frequency, and proximity to the document's beginning.
# Writing a Python script to generate a high-quality Markdown README file for the project.
import os

markdown_content = """# نظام استرجاع المعلومات بالمنطق المضبب للمستندات العربية
### Arabic Information Retrieval System using Fuzzy Logic (C# Desktop Application)

---

## 📌 عن المشروع (About the Project)
هذا النظام هو تطبيق سطح مكتب (Desktop Application) متكامل ومتقدم مخصص لاسترجاع المعلومات (Information Retrieval) من ملفات Word المكتوبة باللغة العربية والمتخصصة في مجال **التسويق**. يعتمد النظام على دمج مفاهيم معالجة اللغة العربية الطبيعية (**Arabic NLP**) مع **المنطق المضبب (Fuzzy Logic)** لتقديم نتائج بحث مرنة وذكية تفوق طرق البحث النصي التقليدية المطابقة تماماً.

يقوم النظام بتحليل المستندات، واستخراج الجذور اللغوية للكلمات، وتطبيق قواعد استنتاج مضببة لتقييم مدى صلة كل مستند بعبارة البحث، ومن ثم ترتيبها تصاعدياً من الأكثر وزناً وصلة إلى الأقل. كما تم تزويد النظام بآليات متطورة لفلترة الكلمات المهملة (Stop Words) ونظام كاش ذكي (Smart Caching) لضمان أقصى سرعة استجابة وأعلى كفاءة في الأداء.

---

## 🚀 الميزات الرئيسية (Key Features)

* **معالجة متقدمة للغة العربية (Arabic NLP & Stemming):** يشتمل النظام على مُحلل صرفي يقوم بإرجاع الكلمات المبحوث عنها والكلمات الموجودة داخل ملفات الـ Word إلى جذورها الثلاثية أو الرباعية (Stemming)؛ مما يضمن العثور على النتائج بغض النظر عن صيغة الاشتقاق (مثل: تسويق، مسوّق، سوقنا -> س و ق).
* **نظام استنتاج مضبب ذكي (Fuzzy Inference System):** لا يعتمد النظام على الإجابات الثنائية (نعم/لا)، بل يحسب "وزن" ودرجة صلة الملف (Relevance Score) بناءً على 3 متغيرات لغوية مدخلة:
    1.  **وجود الكلمة في العنوان الرئيسي (Title Match):** مطابقة كاملة، جزئية، أو منعدمة.
    2.  **كثافة تكرار الكلمة (Term Frequency):** عدد مرات ظهور الجذر في محتوى الملف (منخفض، متوسط، مرتفع).
    3.  **موقع الكلمة (Proximity to Beginning):** مدى قرب الكلمة من بداية المستند (قريب جداً، متوسط، بعيد) باعتبار أن المقدمات والملخصات التنفيذية تحمل الوزن الدلالي الأكبر.
* **تصفية الكلمات الأداتية والمهملة (Stop Words Filtering):** يقوم النظام تلقائياً بفحص كلمة البحث، وفي حال كانت حرف جر، أو أداة جزم، أو نصب، أو نهي (مثل: لا، كم، لن، لم، في، على...)، يرفض النظام عملية البحث ويوجه المستخدم لإدخال كلمة مفتاحية دلالية. هذا يمنع النتائج المضللة الناتجة عن تكرار الحروف العامة.
* **ذاكرة تخزين مؤقتة ذكية (Smart Result Caching):** لتوفير جهد المعالجة (CPU) وقراءة الملفات بشكل متكرر، يتم حفظ نتائج الكلمات المبحوث عنها مسبقاً في الكاش. عند إعادة البحث عن نفس الكلمة، تُعرض النتائج فوراً بزمن استجابة $O(1)$ دون الحاجة لإعادة معالجة الملفات.
* **واجهة مستخدم احترافية (Desktop UI):** واجهة مستخدم سطح مكتب نظيفة، عالية التباين، وسهلة الاستخدام لتقديم تجربة بحث سلسة وسريعة وعرض المستندات المرتبة بالأوزان.

---

## 🛠 التكنولوجيات المستخدمة (Built With)

* **لغة البرمجة:** C# (.NET Framework / .NET Core)
* **نوع التطبيق:** Windows Desktop Application (WPF / Windows Forms)
* **معالجة الملفات:** مكتبات التعامل مع مستندات Microsoft Word (مثل Microsoft Office Interop أو OpenXML / DocX).
* **الخوارزميات:** نظام استنتاج مضبب مخصص (Custom Fuzzy Inference Engine) مدمج مع خوارزمية Stemming للغة العربية.

---

## 📐 آلية عمل النظام (Workflow)
