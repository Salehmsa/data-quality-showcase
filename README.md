# 🔎 Data Quality Analyzer — Showcase

**English** · [العربية](#العربية)

A tool I built that turns **any messy CSV / Excel file** into a clear data-quality report, a ready-to-use pandas cleaning script, and a safely cleaned file — in seconds.

> **The source code is private.** This repository shows what the tool produces. Available for client engagements and on request.

**▶ Live sample report:** https://salehmsa.github.io/data-quality-showcase/ &nbsp;·&nbsp; [Arabic version](https://salehmsa.github.io/data-quality-showcase/report_ar.html)

![Sample report](assets/report_en.png)

## What it does
| Output | Description |
|---|---|
| **Quality report (HTML)** | Quality score, issues ranked by severity (high / medium / low) with a suggested fix for each, per-column profile, missing-value chart, correlation check. English or Arabic (RTL). |
| **Cleaning script (pandas)** | Ready-to-paste code built from the findings. Items that need a business decision are left as commented lines, not automated. |
| **Safely cleaned file** | Trims names and whitespace, converts numbers/dates stored as text, removes exact duplicates. It never imputes, deletes outliers or guesses categories. |
| **Target check (optional)** | Class balance / distribution and possible data leakage. |

## What it detects
- **Structure:** column names with spaces, duplicate names, duplicate rows
- **Types:** numbers stored as text (`"1,334.72 SAR"`, Arabic digits), dates stored as text, mixed date formats
- **Completeness:** missing values by column, ranked
- **Consistency:** `Riyadh` vs `riyadh ` vs `الرياض`, constant columns, identifier-like columns
- **Validity:** negative quantities, rates above 1, placeholder values (`999`, `-1`)
- **Distribution:** outliers, heavy skew, highly correlated pairs

## Sample
[`docs/messy_sales.csv`](docs/messy_sales.csv) is a deliberately broken sales file (615 rows). The report above found 18 issues: inconsistent city spellings, negative quantities, discount rates above 1, prices stored as text, mixed date formats, a constant column, a placeholder `999`, 71% missing notes and 15 duplicate rows.

## Tested on real data
Run on the 39,644-row *Online News Popularity* dataset from my [ML project](https://github.com/Salehmsa/online-news-popularity-classification), it flagged the same invalid rate values I cleaned by hand, and a `-1` placeholder in a keyword column that I had not noticed.

---

## العربية

أداة بنيتها تحوّل **أي ملف CSV أو Excel متسخ** إلى تقرير جودة بيانات واضح، وسكربت pandas للتنظيف، وملف منظّف بأمان — خلال ثوانٍ.

> **الكود المصدري خاص.** هذا الريبو يعرض مخرجات الأداة فقط. متاحة لمشاريع العملاء وعند الطلب.

**▶ تقرير تجريبي مباشر:** https://salehmsa.github.io/data-quality-showcase/report_ar.html

![تقرير عربي](assets/report_ar.png)

**ماذا تنتج:** تقرير جودة (درجة تقديرية، مشكلات مرتبة بالخطورة مع الحل المقترح، ملف لكل عمود)، وسكربت تنظيف جاهز (والقرارات التي تحتاج صاحب العمل تُترك كتعليقات)، وملف منظّف بأمان (لا تعويض ولا حذف للشواذ ولا تخمين)، وفحص اختياري للهدف وتسرّب البيانات.

**ماذا تكتشف:** مسافات أسماء الأعمدة والصفوف المكررة، وأرقام وتواريخ مخزّنة كنص، والمفقود، وتباين الإملاء (`الرياض` و`الرياض `)، والكميات السالبة والنسب الأكبر من 1 والقيم المؤقتة، والقيم المتطرفة والارتباط الشديد.

## Author
**Saleh Mahbub** — [GitHub](https://github.com/Salehmsa)
