🛒 The Product Bundle Project: Decoding Customer Behavior
What is this project about?
Ever wonder why certain items always seem to fly off the shelves together? This project is designed to "listen" to our transaction data to find those hidden connections. By using Market Basket Analysis, we can move away from guessing and start making data-backed decisions on product pairings, store layouts, and discount strategies.

💡 Why does this matter?
Understanding how products interact helps us answer three big questions:

Smart Promotions: If we discount Product A, will it naturally boost the sales of Product B?

Strategic Placement: Which items should be placed near each other (physically or digitally) to make the customer's journey easier?

Customer Loyalty: Who are the customers buying these bundles, and how often are they coming back for them?

🛠 How it Works (The Simple Version)
Cleaning the Noise: We take raw sales data and transform it into a "shopping basket" format—essentially a giant checklist of what was in every single invoice.

Finding the Patterns: We use the Apriori algorithm. It scans thousands of transactions to find rules like: "When people buy a hammer, 80% of the time they also buy nails."

Measuring Strength: We don't just look at what happens most often; we look at what's meaningful. We use three main metrics:

Support: How popular is this combination?

Confidence: How "sure" are we that buying item A leads to item B?

Lift: Is this a real relationship, or just a coincidence because both items are popular?

🚀 The "Best Product" Finder
The heart of this code is a function called bst_products(). You give it a Product ID, and it instantly scans the rules to find the top 10 best items to pair it with.

It doesn't just give you a list; it calculates:

Monthly Shared Invoices: How many times per month these items are actually bought together.

Confidence: The percentage chance that a customer will want the second item.

Customer Overlap: Exactly how many unique customers have bought both, helping us see if the bundle has broad appeal.

📊 Quick Start Guide
To find the best partners for any product, just run:

Python
# Replace 100044 with any Product ID you're curious about
top_matches = bst_products(100044)
print(top_matches)
📦 Requirements
To run this, you'll need a few standard data science tools:

Pandas & NumPy (For data crunching)

MLxtend (The "brain" that finds the associations)

Matplotlib & Seaborn (To visualize the results)
