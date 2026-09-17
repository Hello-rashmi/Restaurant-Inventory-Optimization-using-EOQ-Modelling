# Restaurant-Inventory-Optimization-using-EOQ-Modelling
EOQ-based inventory optimization case study analyzing 100 days of restaurant demand data across 10 ingredients to determine optimal order quantities, reorder points, and inventory costs.

# Problem

Restaurants must balance two competing risks:

Overstocking - higher holding costs, spoilage of perishables
Understocking - stockouts, lost sales, dissatisfied customers

This project builds a repeatable pipeline that answers, for every ingredient:  **how much should we order, how often, and at what stock level should we trigger the next order?**

# Tools
Python (Pandas, NumPy, Matplotlib, Seaborn)

# Method

**1. Clean & adjust** — remove duplicates/invalid rows; compute a seasonality- and waste-adjusted daily demand per item per day.
**2. Aggregate** — average adjusted daily demand, lead time, and price per item across the full 100-day window.
**3. Apply the EOQ model**:
Annual Demand D = avg adjusted daily demand × 365

Reorder Point ROP = avg adjusted daily demand × avg lead time

EOQ Q = √(2DS / H) where S = ordering cost/order (Rs. 100, assumed), H = holding cost/unit/year (20% of unit price, assumed)

Orders per year, cycle time, and total annual cost (purchase + ordering + holding)

**4. Flag risk** — compare latest stock snapshot against the computed reorder point to highlight items needing immediate restocking.
**5. Visualize** — 4 charts covering demand trend, reorder points, EOQ, and the demand–EOQ relationship.

# Key Findings
Eggs and Milk carry the highest annual demand and require the most frequent monitoring.
Eggs have a notably high EOQ (~609 units/order) because their low unit price makes large batch orders cheap to hold a textbook EOQ economies-of-scale case.
Mutton and Paneer, despite high unit prices, have small EOQs , ordering small and often minimizes holding cost on expensive perishables.
