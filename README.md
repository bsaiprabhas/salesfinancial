# salesfinancial
This is a interactive dashboard on sales financial dataset
Here's a clear and professional **description** you can use in your PowerPoint or documentation to explain **how Sales Growth % was calculated in Power BI**:

---

### 📈 **Sales Growth % Calculation – Description**

To measure the change in sales over time, a **Sales Growth %** KPI was created using DAX in Power BI. This measure compares the total sales of the current period with the previous period (month or year), showing the percentage increase or decrease.

#### ✔️ Steps Followed:

1. **Created a Date Table**
   A continuous date table was added using the `CALENDAR` function to ensure accurate time-based analysis.

2. **Linked Date Table**
   The `DateTable[Date]` column was linked to `Sheet1[Date]` via a relationship, enabling proper time intelligence functions.

3. **Defined Base Measure**
   A `Total Sales` measure was defined as:

   ```DAX
   Total Sales = SUM(Sheet1[Sales Amount])
   ```

4. **Created Sales Growth % Measure**
   The formula compares current sales with the same period in the past:

   ```DAX
   Sales Growth % = 
   VAR PrevSales = CALCULATE([Total Sales], DATEADD(DateTable[Date], -1, MONTH))
   RETURN DIVIDE([Total Sales] - PrevSales, PrevSales, 0)
   ```

5. **Visualized with Line Chart or KPI Card**
   The measure was added to visualizations such as line charts or cards, using slicers for time periods to allow dynamic comparisons.

---

Would you like this written for **monthly** or **yearly growth**, or want a **slide-ready version** of this content too?
