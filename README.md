# 🏨 Hotel Booking Cancellation Analysis

**An exploratory data analysis (EDA) project investigating why over a third of hotel bookings get canceled** — built in Python, covering data cleaning, statistical investigation, and business-ready recommendations delivered as a stakeholder report.

---

## 🎯 TL;DR

Analyzed 100K+ hotel bookings across a City Hotel and a Resort Hotel (both located in Portugal) to understand what drives cancellations. Cleaned and validated the raw data, explored cancellation patterns across hotel type, pricing, seasonality, and guest origin, and tested a key assumption statistically rather than taking it at face value — uncovering that **domestic (Portuguese) guests cancel at more than double the rate of most international guests**, not just because they represent the largest customer segment. Delivered findings as a structured Python notebook plus a separate, non-technical **Results & Recommendations report** for stakeholders.

---

## 📖 About This Project

Most beginner EDA projects stop at "make some charts and describe what they show." This project pushes one step further: every major claim is checked against the data before it's treated as a finding.

A good example is the analysis of cancellations by guest country. The initial chart showed Portugal responsible for 62% of all canceled bookings — but since both hotels are *located* in Portugal, that number alone doesn't prove Portuguese guests are more cancellation-prone; it could simply reflect that they're the largest customer base. To test this properly, the analysis pivots from "share of cancellations" to **cancellation rate per country**, confirming that Portuguese guests cancel at ~57%, compared to 17–37% for other major source countries — a genuine behavioral pattern, not a volume artifact.

This project also deliberately avoids overstating correlation as causation (e.g., higher prices *coinciding with* more cancellations is treated as one possible contributing factor among several, including seasonality — not proof of a single cause).

---

## 🏗️ Repository Structure

```
Hotel-Booking-Cancellation-Analysis/
│
├── README.md
├── requirements.txt
│
├── data/
│   └── hotels.csv                                   # Source dataset (see Dataset section)
│
├── notebooks/
│   └── hotel_cancellation_analysis.ipynb             # Full EDA: cleaning → analysis → visualization
│
├── reports/
│   └── Results_and_Recommendations_Report.pdf        # Stakeholder-facing summary
│
└── images/
    ├── reservation_status_count.png
    ├── cancellation_by_hotel_type.png
    ├── adr_trend_by_hotel.png
    ├── lost_revenue_per_month.png
    └── cancellation_rate_by_country.png
```

---

## 🔑 Key Insights

| Finding | Detail |
|---|---|
| **Overall cancellation rate** | 37% of all bookings were canceled |
| **Hotel type matters** | City Hotel cancellation rate (~42%) is notably higher than Resort Hotel (~28%) |
| **Guest origin matters more than volume** | Portuguese guests cancel at **~57%**, vs. 17–37% for other top source countries — even after correcting for Portugal simply having the most bookings |
| **Seasonality** | January has the fewest confirmed bookings but the highest number of cancellations; August has the highest volume of both confirmed and canceled bookings |
| **Price is a contributing factor, not the sole cause** | Cancellations tend to be more common during higher average daily rate (ADR) periods, but this overlaps with seasonal demand, so it's treated as one factor among several rather than a proven single cause |

📄 Full write-up with charts and business recommendations: [`reports/Results_and_Recommendations_Report.pdf`](./reports/Results_and_Recommendations_Report.pdf)

---

## 🧹 Data Cleaning

- Removed columns with excessive missing data (`agent`, `company`)
- Dropped rows with missing critical fields (`children`, `country`)
- Identified and removed pricing outliers (`adr`) using boxplot inspection
- Converted `reservation_status_date` to proper datetime format
- Standardized `is_canceled` to boolean for clarity

---

## 💡 Recommendations

- Introduce a partial non-refundable deposit or a stricter cancellation window for domestic (Portuguese) bookings, where cancellation risk is highest.
- Monitor cancellation rate by country over time to confirm the pattern is stable and not seasonal.
- Offer early-bird incentives that reward guests for confirming bookings early, targeting the low-commitment booking behavior behind high cancellation rates — rather than generic advertising campaigns.
- Launch targeted promotions in January specifically, since it combines the lowest confirmed-booking volume with the highest cancellation count.

---

## 🛠️ Tech Stack

- **Language:** Python
- **Data Handling:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn, Plotly
- **Environment:** Jupyter Notebook

---

## 🚀 Getting Started

```bash
# 1) Clone the repository
git clone https://github.com/ahmedkhedr-xrs/Hotel-Booking-Cancellation-Analysis.git
cd Hotel-Booking-Cancellation-Analysis

# 2) Install dependencies
pip install -r requirements.txt

# 3) Open the notebook
jupyter notebook notebooks/hotel_cancellation_analysis.ipynb
```

---

## 🗂️ Dataset

Public dataset: **[Hotel Booking Demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)** (Kaggle), originally published by Antonio, Almeida & Nunes (2019) in *Data in Brief*. Contains ~120K bookings for a Resort Hotel (Algarve, Portugal) and a City Hotel (Lisbon, Portugal) between July 2015 and August 2017, with all personally identifying information removed.

---

## 👤 Author

Ahmed Farid Khedr — built as a Data Analyst portfolio project covering the full exploratory analysis lifecycle: data cleaning, statistical validation of assumptions, visualization, and translating findings into a business-ready recommendations report.

🔗 [GitHub](https://github.com/ahmedkhedr-xrs) &nbsp;|&nbsp; 🔗 [LinkedIn](https://linkedin.com/in/ahmed-fareed-khedr)
