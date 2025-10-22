
# 📊 Amazon Prime Video Insights: Genre, Ratings & Trends Over Time

## 🚀 Project Overview  
This Power BI dashboard project offers data-driven insights into the Amazon Prime Video content library, focusing on trends across genres, countries, and time. It helps analyze user preferences and content strategy based on IMDb/TMDB ratings, votes, and talent appearances.

The project explores:
- What genres dominate the platform
- Country-wise content distribution
- How ratings vary over time
- Which actors and directors contribute the most

---

## 🎯 Business Context  
In today's competitive streaming industry, platforms like Amazon Prime Video continuously expand their content libraries to engage global audiences. Understanding what content performs best, which genres are growing, and how regional production affects the platform are vital to making strategic content decisions.

This project enables:
- Media analysts to identify viewer patterns
- Content teams to refine acquisition strategies
- Data enthusiasts to explore real-world entertainment data

---

## 🗃️ Dataset Description

Two CSV files were used in this project, combining both categorical and numerical data:

### 📁 titles.csv
- `id`, `title`, `show_type`, `release_year`, `description`, `age_certification`
- `runtime`, `genres`, `production_countries`, `seasons`
- `imdb_id`, `imdb_score`, `imdb_votes`, `tmdb_score`, `tmdb_popularity`

### 📁 credits.csv
- `person_ID`, `id`, `name`, `character_name`, `role` (ACTOR or DIRECTOR)

🔢 **Data Stats**:
- 9617 Titles  
- 124K+ Credits  
- 15 Fields (titles), 5 Fields (credits)

---

## 🧹 Data Cleaning & Transformation

Performed using **Power Query**:
- Removed duplicates and nulls  
- Normalized `genres` and `production_countries` into separate relational tables  
- Split list fields using `Text.Split`  
- Converted types for scoring, dates, etc.

---

## 🧠 Data Modeling

- Star schema used in Power BI  
- One-to-many: `titles[id]` → `credits[id]`  
- Flattened many-to-many relationships for genres & countries  
- Created custom measures and calculated columns

---

## 🧮 Key DAX Measures

```dax
Total Titles = COUNT(titles[id])
Total Movies = CALCULATE(COUNT(titles[id]), titles[show_type] = "MOVIE")
Total Shows = CALCULATE(COUNT(titles[id]), titles[show_type] = "SHOW")

Avg IMDb Score = AVERAGE(titles[imdb_score])
Avg TMDB Score = AVERAGE(titles[tmdb_score])
Total IMDb Votes = SUM(titles[imdb_votes])
```

---

## 🎨 Dashboard Design Highlights

- **KPI Cards**: Ratings, votes, content counts  
- **Charts**: Line (score over time), Bar (genre scores), Pie (content ratio), Scatter (talent), Map (top producing countries)  
- **Theme**: Dark UI with blue accents  
- **UX**: Slicers, filters, intuitive layout

---

## 📈 Key Insights

- Avg IMDb Score: 5.96  
- Documentaries lead in average scores  
- USA, UK, and India produce the most content  
- Shows only 12.7% of the content  
- Directors show stronger correlation with higher IMDb scores

---

## 🧩 Challenges Faced

- Handling multi-value categorical fields  
- Creating normalized structure without losing filtering ability  
- Making the design compact but informative

---

## 🔮 Conclusion

The dashboard provides meaningful insights into Prime Video's content library and audience preferences. It showcases real-world data modeling, visualization techniques, and storytelling using Power BI.

---

## 📁 Repository Structure

```
📦 Amazon-Prime-Video-PowerBI
├── 📊 Dashboard Screenshot.png
├── capstone project.pbix
├── 📄 README.md
```

---

## 📷 Dashboard Preview

<img width="1846" height="1041" alt="image" src="https://github.com/user-attachments/assets/71fa25e5-64eb-4862-bfbd-3fba8ecd5a3c" />


---

## 💡 Tools & Technologies

- Power BI  
- Power Query  
- DAX  
- Bing Maps  
- CSV (JustWatch source)

---

## 📌 Author

**👨‍💻 Manoj B.**  
Data-focused electronics engineer passionate about transforming datasets into impactful visuals.  
[🔗 LinkedIn](#) | [🌐 Portfolio](#) | [📧 Email](#)

---

> _This project is for educational and analytical purposes only. The data is used under fair use for visualization learning._
