# Uber Ride Bookings – Data Analysis Dashboard (Tableau)

### Data Cleaning, Geospatial Mapping & KPI Storytelling in Tableau

---

### 📌 Project Overview

This project takes a raw, messy ride-bookings export and turns it into a Tableau story covering overall performance, vehicle mix, revenue, cancellations, and ratings — the kind of end-to-end dashboard a mobility analyst would hand to operations leadership.

The project follows an end-to-end workflow:

**Raw Excel Export → Data Cleaning → Geocoding → Tableau Data Model → Calculated Fields → KPI Dashboard + Story**

---

### 🏢 Industry

Ride-hailing / Mobility

---

### 💡 Business Scenario

The raw export (`ncr_ride_bookings`) held 150,000 ride bookings across the Delhi NCR region for 2024, with pickup/drop locations recorded as place names rather than coordinates, inconsistent completion flags, and no easy way to group cancellations or vehicle types for reporting. The task was to clean the export, geocode every pickup/drop location, and build a Tableau dashboard covering booking volume, vehicle mix, revenue, cancellation patterns, and ratings.

---

### 📊 Dataset

`Uber_dataset.xlsx` — 3 sheets.

| Sheet | Columns | What it holds |
|---|---|---|
| **ncr_ride_bookings** | Date, Time, Booking ID, Booking Status, Customer ID, Vehicle Type, Pickup/Drop Location, Avg VTAT/CTAT, cancellation & incomplete-ride reasons, Booking Value, Ride Distance, Driver/Customer Ratings, Payment Method | Raw export — 150,000 bookings, 21 columns |
| **Cleaneddataset** | All raw columns + Is Completed, Is Cancelled, Cancelled By, Vehicle Group, Pickup Lat/Long, Drop Lat/Long | Cleaned & enriched dataset — 148,767 bookings, 29 columns |
| **LocationCoordinates** | Location Name, Latitude, Longitude | Lookup table of 176 named locations used to geocode every pickup/drop point |

---

### 🧹 Data Cleaning & Preparation

- Removed duplicate and invalid booking rows, taking the raw 150,000-row export down to **148,767 clean bookings**
- Added derived flags — **Is Completed**, **Is Cancelled**, **Cancelled By** (Driver/Customer) — so Booking Status could be sliced consistently across every dashboard tab
- Grouped the 7 raw vehicle types into a simpler **Vehicle Group** (merging Bike + E-Bike into "Bike/E-Bike") for cleaner charting
- Geocoded every Pickup and Drop Location against the 176-location lookup table to produce **Pickup Lat/Long** and **Drop Lat/Long**, powering the Pickup Demand Map

---

### 📈 Dashboard Highlights

The Tableau workbook is a multi-tab story: **Overall · Vehicle Type · Revenue · Cancellation · Ratings · Story 1**, backed by detail sheets — Pickup Demand Map, Booking Status Analysis, Revenue by Payment Method, Revenue by Vehicle Type, Cancelled Rides by Customers, Cancelled Rides by Drivers, Customer Ratings, Driver Ratings.

- **KPI card:** Total Bookings, with a Month filter/parameter
- **Pickup Demand Map** — geocoded pickup density across Delhi NCR (Panipat to Faridabad, Gurugram to Ghaziabad)
- **Booking Status Analysis** — Completed vs. Cancelled by Driver, Cancelled by Customer, No Driver Found, Incomplete
- **Revenue by Payment Method** and **Revenue by Vehicle Type**
- **Cancelled Rides by Customers** and **Cancelled Rides by Drivers** — breakdown by stated reason
- **Customer Ratings** and **Driver Ratings** distributions

Across the cleaned dataset (Jan–Dec 2024): **148,767 total bookings**, a **62% completion rate** (92,248 completed), **26,789** cancelled by drivers, **10,402** cancelled by customers, **10,401** with no driver found, and **8,927** incomplete rides. Total booking value across all rides is **≈₹5.14 crore**, with an average customer rating of **4.40** and average driver rating of **4.23**. Auto is the most-booked vehicle type (37,129 rides) and UPI the most-used payment method (45,542 rides).

---

### 🛠️ Technology / Tools

- Tableau Desktop / Public (dashboard, story, calculated fields, parameters)
- Microsoft Excel (data cleaning, derived columns, geocoding lookup)
- Mapbox / OpenStreetMap (base map for the Pickup Demand Map)

---

### 🔄 Project Workflow

```
Raw Excel Export (150,000 rows — ncr_ride_bookings)
      ↓
Data Cleaning in Excel (duplicates/invalid rows removed → 148,767 rows; Is Completed, Is Cancelled, Cancelled By, Vehicle Group added)
      ↓
Geocoding (Pickup/Drop Location matched against 176-location lookup table for Lat/Long)
      ↓
Tableau Data Model (Cleaneddataset + LocationCoordinates)
      ↓
Calculated Fields & Parameters (Booking Status grouping, Vehicle Group, Month filter)
      ↓
KPI Dashboard + Story (Overall, Vehicle Type, Revenue, Cancellation, Ratings)
```

---

### 📁 Project Structure

```
Uber-Data-Analysis-Tableau-Dashboard/
│
├── Uber_Dataset_Analysis_Dashboard.twbx
├── Uber_dataset.xlsx
├── Uber_Dataset_Analysis_Dashboard.png
├── Uber_Dataset_Analysis_Dashboard.mp4
└── README.md
```

---

### 📌 Project Deliverables

- Tableau packaged workbook (`.twbx`) with the full dashboard and story
- Cleaned, geocoded dataset (`.xlsx`) with derived fields for reporting
- Dashboard screenshot and video walkthrough

---

### 🔗 Connect

[Jeisa Mathew LinkedIn](https://www.linkedin.com/in/jeisamathew/) • [GitHub](https://github.com/JEISAMATHEW)
