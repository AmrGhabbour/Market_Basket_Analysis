# 🛒 The Product Bundle Project: Decoding Customer Behavior

### What is this project about?
Ever wonder why certain items always seem to fly off the shelves together? This project is designed to "listen" to our transaction data to find those hidden connections. By using **Market Basket Analysis**, we can move away from guessing and start making data-backed decisions on product pairings, store layouts, and discount strategies.

---

### 💡 Why does this matter?
Understanding how products interact helps us answer three big questions:
1. **Smart Promotions:** If we discount Product A, will it naturally boost the sales of Product B?
2. **Strategic Placement:** Which items should be placed near each other (physically or digitally) to make the customer's journey easier?
3. **Customer Loyalty:** Who are the customers buying these bundles, and how often are they coming back for them?

---

### 🛠 How it Works (The Simple Version)

* **Cleaning the Noise:** We take raw sales data and transform it into a "shopping basket" format—essentially a giant checklist of what was in every single invoice.
* **Finding the Patterns:** We use the **Apriori algorithm**. It scans thousands of transactions to find rules like: *"When people buy a hammer, 80% of the time they also buy nails."*
* **Measuring Strength:** We don't just look at what happens most often; we look at what's *meaningful*. We use three main metrics:
    * **Support:** How popular is this combination across all sales?
    * **Confidence:** How "sure" are we that buying Item A leads to Item B?
    * **Lift:** Is this a real relationship, or just a coincidence because both items happen to be popular?

---

### 🚀 The "Best Product" Finder
The heart of this code is a function called `bst_products()`. You give it a Product ID, and it instantly scans the rules to find the top 10 best items to pair it with. 

It doesn't just give you a list; it calculates:
* **Monthly Shared Invoices:** How many times per month these items are actually bought together.
* **Confidence:** The percentage chance that a customer will want the second item.
* **Customer Overlap:** Exactly how many unique customers have bought both, helping us see if the bundle has broad appeal.

---

### 📊 Quick Start Guide
To find the best partners for any product, simply run the following in your environment:

```python
# Replace 100044 with any Product ID you are curious about
top_matches = bst_products(100044)
print(top_matches)
```



# 🛒 مشروع تحليل سلة المشتريات (Market Basket Analysis)

### المشروع ده عبارة عن إيه؟
عمرك سألت نفسك ليه السوبر ماركت بيحط العيش جنب الجبنة؟ أو ليه لما بتشتري موبايل، الموقع بيقترح عليك "جراب" و"سكرينة"؟
المشروع ده وظيفته إنه "يسمع" لكلام البيانات (المناديب والفواتير) عشان يطلع لنا العلاقات المستخبية بين المنتجات. إحنا هنا مش بنخمن، إحنا بنخلي لغة الأرقام تقول لنا إيه اللي بيتباع مع إيه.

---

### 💡 إحنا بنعمل كل ده ليه؟
فهمنا للعلاقات دي بيفتح لنا أبواب كتير في البيزنس:
1. **عروض ذكية (Bundles):** لو عرفنا إن المنتج (أ) بيسحب معاه المنتج (ب)، نعمل لهم عرض "باكيدج" مع بعض ونزود المبيعات.
2. **رصة الرفوف:** نحط المنتجات اللي "بتحب بعض" قريبين من بعض، سواء في المخزن أو في الكتالوج، عشان نسهل على الزبون.
3. **تنشيط الأصناف الركدة:** لو فيه صنف نايم، نشوف أكتر صنف "بيحبه" ونعمل بينهم ربط في الدعاية.

---

### 🛠️ إزاي الكود ده شغال؟ (الخطوات التعليمية)

#### 1. قلبنا البيانات (The Pivot Table)
بدأنا بجدول مبيعات عادي، وحولناه لشكل "فواتير". كل سطر عبارة عن رقم فاتورة، وكل عمود عبارة عن كود منتج. لو المنتج موجود في الفاتورة بنحط (1)، مش موجود بنحط (0).

#### 2. خوارزمية "أبريوري" (Apriori Algorithm)
دي اللي بتدور على "العِشرة" بين المنتجات. ميزتها إننا بنحدد لها "أقل تكرار" (Support) عشان ما توجعش دماغنا بعلاقات صدفة حصلت مرة واحدة في السنة.

#### 3. إزاي بنعرف إن العلاقة قوية؟ (المقاييس)
* **الدعم (Support):** الصنفين دول ظهروا مع بعض كام مرة من وسط كل الفواتير؟ (يعني الحركة عليهم قد إيه؟).
* **الثقة (Confidence):** لو الزبون حط المنتج (أ) في السلة، بنسبة كام % هيحط معاه المنتج (ب)؟ (قوة الارتباط).
* **الرفع (Lift):** ده أهم واحد! بيقولنا هل المنتج (ب) بيتباع مع (أ) "عشان هما فعلًا مرتبطين"، ولا عشان (ب) أصلًا صنف مشهور وبيتباع مع أي حاجة وخلاص؟ (لو الرقم أكبر من 1 يبقى فيه ارتباط حقيقي).

---

### 🚀 المحرك بتاعنا: دالة `bst_products()`
الدالة دي هي "الخلاصة". إحنا طورناها عشان تبقى طيارة في التنفيذ (Optimized). لما تديها كود أي منتج، هي بتعمل الآتي:
1. بتجرد كل القواعد المرتبطة بالمنتج ده.
2. بتحسب لك "متوسط الفواتير المشتركة في الشهر" عشان تبقى عارف حجم الشغل.
3. بتقولك "كام عميل مختلف" اشترى الصنفين دول مع بعض، عشان نتأكد إنها مش حركة عميل واحد بيخزن!

---

### 📊 أجرب الكود إزاي؟
الموضوع بسيط، بعد ما تشغل الكود، استدعي الدالة بكود المنتج اللي انت عايزه:

```python
# حط كود المنتج مكان الرقم ده وهتطلع لك "أجدع" 10 ترشيحات
top_matches = bst_products(100044)
print(top_matches)
