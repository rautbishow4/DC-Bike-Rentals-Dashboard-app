
# 🚲 Washington D.C. Bike Rentals Dashboard

An interactive **Streamlit dashboard** for exploring bike rental demand in **Washington, D.C.** using the Capital Bikeshare bike-sharing dataset from **2011–2012**.

The dashboard analyzes how **time, seasonality, day of the week, and working-day patterns** influence bike rental demand, while also comparing **casual and registered users**.

---

## 📊 Project Overview

Bike-sharing systems generate large amounts of operational data that can be used to understand demand patterns and improve transportation planning.

This project transforms the Washington D.C. bike rental dataset into an interactive analytical dashboard that allows users to explore:

* Hourly rental patterns
* Daily rental patterns
* Monthly demand
* Seasonal demand
* Time-of-day demand
* Casual vs. registered users
* Working-day vs. non-working-day behavior
* Key rental performance indicators

The dashboard is designed as an **exploratory data visualization application** using Python and Streamlit.

---

## 🎯 Objectives

The main objectives of this project are to:

1. Understand temporal patterns in bike rental demand.
2. Identify peak rental hours.
3. Compare rental activity across days of the week.
4. Analyze monthly and seasonal variations.
5. Compare casual and registered customers.
6. Explore differences between working days and non-working days.
7. Present the findings through an interactive dashboard.

---

## 🖥️ Dashboard

The application is built with **Streamlit** and provides interactive filters through the sidebar.

### Available Filters

Users can dynamically filter the dataset by:

* **Year**

  * Both
  * 2011
  * 2012

* **Working Day**

  * All
  * Working day
  * Non-working day

* **Season**

  * Spring
  * Summer
  * Fall
  * Winter

All KPI calculations and visualizations update based on the selected filters.

---

## 📌 Key Performance Indicators

The dashboard displays five KPIs:

| KPI                        | Description                                          |
| -------------------------- | ---------------------------------------------------- |
| **Total Rentals**          | Total number of bike rentals in the selected dataset |
| **Casual Rentals**         | Rentals made by casual users                         |
| **Registered Rentals**     | Rentals made by registered users                     |
| **Average Hourly Rentals** | Average number of rentals per hourly observation     |
| **Peak Hour**              | Hour with the highest average rental count           |

These metrics provide a quick overview of bike rental demand before exploring the detailed visualizations.

---

## 📈 Visualizations

### 1. Mean Rentals by Hour of Day

A line chart showing average bike rentals for each hour of the day.

This visualization helps identify:

* Peak commuting periods
* Low-demand periods
* Morning and evening demand patterns
* Overall hourly demand behavior

---

### 2. Mean Rentals by Day of Week

A bar chart comparing average rental demand from Monday through Sunday.

This allows users to investigate differences between:

* Weekdays
* Fridays
* Saturdays
* Sundays

---

### 3. Mean Rentals by Month

A monthly trend visualization showing how average rental demand changes throughout the year.

This helps identify periods of:

* Increasing demand
* Seasonal peaks
* Seasonal declines

---

### 4. Mean Rentals by Season

A bar chart comparing average rental activity across:

* Spring
* Summer
* Fall
* Winter

This provides a high-level view of seasonal differences in bike usage.

---

### 5. Mean Rentals by Period of Day

The dashboard groups hours into four periods:

| Period           | Hours       |
| ---------------- | ----------- |
| 🌙 **Night**     | 00:00–05:00 |
| 🌅 **Morning**   | 06:00–11:00 |
| ☀️ **Afternoon** | 12:00–17:00 |
| 🌆 **Evening**   | 18:00–23:00 |

The visualization displays the mean rental count together with a **95% confidence interval**.

---

## 🗃️ Dataset

The project uses the **Capital Bikeshare / Kaggle Bike Sharing Demand dataset**.

The dataset contains hourly bike rental observations from Washington, D.C. for **2011 and 2012**.

The application uses the `train.csv` file included in the repository.

### Important Variables

The analysis uses variables including:

| Variable     | Description                       |
| ------------ | --------------------------------- |
| `datetime`   | Date and time of the observation  |
| `season`     | Season category                   |
| `workingday` | Whether the day is a working day  |
| `casual`     | Number of casual-user rentals     |
| `registered` | Number of registered-user rentals |
| `count`      | Total rental count                |

Additional analytical variables are generated from `datetime`, including:

* `year`
* `month`
* `hour`
* `dayofweek`
* `season_name`
* `day_period`

These transformations are performed directly in `app.py`.

---

## 🔄 Data Processing Workflow

The dashboard follows this workflow:

```text
                train.csv
                    │
                    ▼
             Load Dataset
                    │
                    ▼
          Convert datetime column
                    │
                    ▼
        Feature Engineering
        ┌───────────┼───────────┐
        ▼           ▼           ▼
       Year       Month        Hour
        │           │           │
        └───────────┼───────────┘
                    │
             Day of Week
                    │
             Season Name
                    │
             Period of Day
                    ▼
             Apply Filters
                    │
                    ▼
            KPI Calculations
                    │
                    ▼
             Visualizations
```

---

## 🛠️ Technologies Used

The project is built using:

* **Python**
* **Streamlit** – Interactive web dashboard
* **Pandas** – Data manipulation and analysis
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical visualization

These dependencies are specified in `requirements.txt`.

---

## 📁 Project Structure

```text
DC-Bike-Rentals-Dashboard-app/
│
├── app.py
├── train.csv
├── requirements.txt
└── README.md
```

### File Descriptions

| File               | Purpose                              |
| ------------------ | ------------------------------------ |
| `app.py`           | Main Streamlit dashboard application |
| `train.csv`        | Bike rental dataset                  |
| `requirements.txt` | Python dependencies                  |
| `README.md`        | Project documentation                |

The current GitHub repository contains these four project files.

---

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/rautbishow4/DC-Bike-Rentals-Dashboard-app.git
```

### 2. Navigate to the Project

```bash
cd DC-Bike-Rentals-Dashboard-app
```

### 3. Create a Virtual Environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Dashboard

```bash
streamlit run app.py
```

The application will normally be available at:

```text
http://localhost:8501
```

---

## 📊 Example Questions the Dashboard Can Answer

The dashboard can be used to investigate questions such as:

* What time of day has the highest bike rental demand?
* How does demand differ between weekdays and weekends?
* Which months have the highest average rental activity?
* How does bike usage change across seasons?
* How large is the difference between casual and registered users?
* How does demand change between working and non-working days?
* Which periods of the day have the greatest variability in rental demand?

---

## 🔎 Analytical Approach

The project uses **descriptive and exploratory data analysis** rather than predictive modeling.

The main analytical approach is:

1. Load the bike-sharing dataset.
2. Convert timestamps into usable date/time features.
3. Create categorical time periods.
4. Apply interactive filters.
5. Aggregate rental counts.
6. Calculate KPIs.
7. Visualize demand patterns.
8. Allow users to interactively explore the results.

The dashboard uses cached data loading through Streamlit's `@st.cache_data` functionality to avoid repeatedly processing the CSV during interaction.

---

## 💡 Potential Business Applications

The analysis can support questions relevant to bike-sharing operations, including:

* **Fleet planning:** identifying periods of high demand.
* **Bike availability:** understanding when demand is likely to increase.
* **Operational planning:** comparing working-day and non-working-day patterns.
* **Seasonal planning:** understanding demand changes throughout the year.
* **Customer analysis:** distinguishing behavior between casual and registered users.
* **Transportation planning:** identifying recurring demand patterns.

---

## ⚠️ Limitations

A few limitations should be considered when interpreting the dashboard:

* The analysis covers the **2011–2012** dataset.
* The dashboard is primarily descriptive rather than predictive.
* Weather variables available in the source dataset are not currently visualized directly.
* The dashboard does not currently include station-level analysis.
* Rental demand patterns from 2011–2012 may not represent current Washington D.C. bike-sharing behavior.
* The application depends on the included `train.csv` dataset.

---

## 🔮 Future Improvements

Potential extensions include:

* [ ] Add weather-based analysis
* [ ] Add temperature and humidity analysis
* [ ] Add wind-speed analysis
* [ ] Add casual vs. registered user comparison charts
* [ ] Add interactive date-range filtering
* [ ] Add weekday/weekend classification
* [ ] Add predictive demand forecasting
* [ ] Add machine-learning models
* [ ] Add station-level analysis
* [ ] Add downloadable filtered data
* [ ] Add interactive Plotly charts
* [ ] Deploy the dashboard using Streamlit Community Cloud

---

## 🤝 Contributing

Contributions and improvements are welcome.

1. Fork the repository.
2. Create a feature branch:

```bash
git checkout -b feature/your-feature
```

3. Make your changes.
4. Commit your changes:

```bash
git commit -m "Add your feature"
```

5. Push your branch:

```bash
git push origin feature/your-feature
```

6. Open a Pull Request.

---

## 👤 Author

**Bishownath Raut**

GitHub:

https://github.com/rautbishow4

Project Repository:

https://github.com/rautbishow4/DC-Bike-Rentals-Dashboard-app

---

## ⭐ Acknowledgements

* **Capital Bikeshare** for the underlying bike-sharing data.
* **Kaggle** for providing the Bike Sharing Demand dataset.
* **Streamlit** for the interactive dashboard framework.
* **Pandas, Matplotlib, Seaborn, NumPy** for data analysis and visualization.

---



If you plan to distribute or reuse the project, consider adding an appropriate license such as the **MIT License**.
