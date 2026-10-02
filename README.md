# 🚗 Toyota-Astra Telematics Analytics Dashboard

End-to-end telematics analytics solution for **PT Toyota-Astra Motor (TAM)**. The project integrates connected-car, customer, partner, and support data into a unified analytics layer and delivers **7 interactive dashboards** that monitor the full telematics lifecycle, from device registration and subscription to driving behavior, vehicle health, partner usage, and after-sales support.

---

## 🎯 Key Business Value

- **Operational visibility:** single view of the connected-vehicle base across fleet and retail
- **Process improvement:** funnel analysis pinpoints drop-offs in device, document, and app registration
- **Customer insight:** demographics and driving behavior support targeted marketing and insurance products
- **Proactive maintenance:** warning and device-health monitoring reduces downtime
- **Service quality:** ERA ticket tracking improves response planning by area and category
- **Data monetization:** partner usage tracking supports billing and partnership decisions with leasing and insurance companies

---

## 👤 My Role

- Gathered requirements with business stakeholders and defined telematics KPIs
- Designed ETL workflows using **SSIS**, with **Python** for data cleansing and transformation
- Built data models and KPI logic in **SQL**
- Implemented a unified virtual data layer with **Denodo** to integrate multiple sources
- Designed and delivered 7 interactive dashboards with consistent filters and navigation
  
---

## 📌 Project Highlights

- **7 dashboards** covering operations, sales, customer behavior, vehicle health, support, and partners
- **End-to-end data pipeline**: ETL with SSIS, Python & SQL, plus data virtualization with Denodo
- **Unified filtering** across all pages: Year, Month, Sub Area, Dealer, and Vehicle Model
- **Geo-analytics** to map vehicle and customer distribution across Greater Jakarta (Jabodetabek)
- **Funnel & journey tracking** to measure conversion from device registration to app activation

---

## 🛠️ Tech Stack

| Layer | Tools | Purpose |
|---|---|---|
| Data Extraction & Loading | **SSIS** | Scheduled ETL jobs to extract and load data from operational sources |
| Data Processing | **Python** | Cleansing, transformation, and validation of large telematics datasets |
| Data Modeling & Querying | **SQL** | Staging, data modeling, KPI logic, and aggregation |
| Data Virtualization | **Denodo** | Unified semantic layer combining multiple sources without physical replication |
| Visualization | BI Dashboards | Interactive reporting with drill-down filters and tooltips |

---

## 🏗️ Data Architecture

```
┌──────────────────────┐     ┌──────────────────┐     ┌──────────────────┐     ┌──────────────────┐
│   Source Systems     │     │   ETL Layer      │     │  Virtual Layer   │     │  Presentation    │
│                      │     │                  │     │                  │     │                  │
│ • Telematics devices │ ──► │ • SSIS packages  │ ──► │ • Denodo views   │ ──► │ • 7 interactive  │
│ • Vehicle & dealer   │     │ • Python scripts │     │ • Unified KPI    │     │   dashboards     │
│ • Customer & app     │     │ • SQL staging &  │     │   definitions    │     │ • Global filters │
│ • Support tickets    │     │   data models    │     │                  │     │                  │
│ • Leasing/insurance  │     │                  │     │                  │     │                  │
└──────────────────────┘     └──────────────────┘     └──────────────────┘     └──────────────────┘
```

---

## 🎛️ Global Filters

All dashboards share the same filter panel so users can slice data consistently across pages:

| Filter | Description |
|---|---|
| **Year / Month** | Time period of analysis |
| **Sub Area** | Regional breakdown (e.g., Jakarta Barat, Jakarta Utara, Jakarta Timur) |
| **Dealer** | Dealer-level performance |
| **Vehicle Model** | Avanza, Innova, Rush, Yaris, Agya, Corolla, Alphard, etc. |

A **Home Page** button on each dashboard provides navigation back to the main menu.

---

## 📊 Dashboard Pages

### 1. Telematics Status Dashboard

![Telematics Status](Telematic%20Status.jpg)

**Purpose:** Executive overview of the entire telematics installed base and its activation pipeline.

| Visual | Function |
|---|---|
| **Vehicle Distribution (map)** | Bubble map of telematics vehicles by area; tooltip shows area, model, total vehicles, and retail vs fleet split |
| **Total Subscription (treemap)** | Subscription share by vehicle model |
| **KPI Cards** | Total telematics, fleet, and retail vehicles |
| **Telematics Distribution** | Device count by provider (LDCM vs Teltonica) per city |
| **Telematics Distribution by City** | Fleet vs retail vehicles in Jakarta, Bandung, and Bogor |
| **Telematics Journey (funnel)** | Conversion from *Device Register → Vehicle Register → Vehicle Assemble → M Toyota Register*, with overall conversion rate |

**Business questions answered:** How many vehicles are connected? Where are they located? Which device provider dominates each city? Where do vehicles drop off before app activation?

---

### 2. Telematics Fleet Dashboard

![Telematics Fleet](Telematic%20Fleet.jpg)

**Purpose:** Monitor telematics adoption among corporate / fleet customers.

| Visual | Function |
|---|---|
| **Vehicle Distribution (map)** | Geographic spread of fleet vehicles |
| **Total Subscription (treemap)** | Fleet subscriptions by model |
| **Total Telematics Vehicle** | Headline KPI for connected fleet units |
| **Telematics Distribution** | Device provider split per city |
| **Telematics Distribution by City** | Fleet vs retail comparison per city |
| **Telematics Distribution by Customer** | Fleet breakdown by customer category (Rental vs Office) |
| **Telematics Journey** | Document flow: *TAM Doc Receive → Branch Doc Receive → Customer Doc Receive → M Toyota Register* |

**Business questions answered:** Which customer segments drive fleet adoption? Where are document handovers delayed in the fleet onboarding process?

---

### 3. Telematics Retail Dashboard

![Telematics Retail](Telematic%20Retail.jpg)

**Purpose:** Track telematics adoption and sales progress for individual (retail) customers.

| Visual | Function |
|---|---|
| **Vehicle Distribution (map)** | Geographic spread of retail vehicles |
| **Total Subscription (treemap)** | Retail subscriptions by model |
| **Total Telematics Vehicle** | Headline KPI for connected retail units |
| **Telematics Distribution** | Device provider split per city |
| **Funneling Retail Sales** | Sales pipeline status (*Status Pengajuan* / application and *Status AFI*) split into Done vs Process, per city |
| **Telematics Journey** | Document flow from TAM to customer and M Toyota app registration |

**Business questions answered:** How many retail applications are still in process? Which city has the biggest backlog? How effectively are retail customers onboarded to the app?

---

### 4. Telematics User Activity Dashboard

![User Activity](User%20Activity.jpg)

**Purpose:** Understand who the customers are and how they drive and use telematics features.

| Visual | Function |
|---|---|
| **Customer Profile Telematics (map)** | Customer locations with tooltip for model, total vehicles, assembly year, and complaint count |
| **Owner Profile** | Owner demographics by gender and age group (25–55 and >55) per vehicle model |
| **Most Used Feature** | Feature usage comparison per model |
| **Driving Behaviour** | Average driving score gauge (0–100) plus counts of sudden acceleration, sudden deceleration, and sudden cornering |
| **Number of Trip** | Total trips recorded |
| **Drive Score (treemap)** | Driving score by model, with total mileage in tooltip |

**Business questions answered:** Which demographic owns which model? Which features deliver the most value? Which models show riskier driving patterns? This supports product, marketing, and insurance use cases.

---

### 5. Telematics Vehicle Activity Dashboard

![Vehicle Activity](Vehicle%20Activity.jpg)

**Purpose:** Monitor vehicle health and telematics device reliability.

| Visual | Function |
|---|---|
| **Total Warning Notification (donut)** | Warning breakdown by type (Oil Pressure Switch vs Fuel Filter Switch) |
| **Total Device Trouble** | Monthly trend of broken telematics devices |
| **Total Vehicle Warning** | Warning volume per vehicle model |
| **Device Status** | Count of devices in GOOD vs NOT GOOD condition |

**Business questions answered:** Which warnings occur most often? Are device failures seasonal? Which models need preventive maintenance attention? How healthy is the device fleet overall?

---

### 6. Telematics Support Dashboard (ERA)

![ERA Support](Ticket%20ERA%20Support.jpg)

**Purpose:** Track after-sales and Emergency Roadside Assistance (ERA) ticket performance.

| Visual | Function |
|---|---|
| **Total Ticket by Month** | Monthly ticket volume trend |
| **KPI Cards** | Total tickets submitted, on progress, and closed |
| **Total Ticket by Category** | Tickets by type: Accident, Regular ERA, Device Trouble, E-Care Preventive, Lost Car |
| **ERA Support Frequency** | Ticket status distribution (Open, On-Progress, Closed) |
| **ERA Support (treemap)** | Ticket volume by area (Jakarta Pusat, Barat, Utara, Selatan, Depok, Bekasi, Tangerang) |

**Business questions answered:** What is the ticket resolution rate? Which issue categories dominate? Which areas need more support resources? Are there seasonal peaks in support demand?

---

### 7. Telematics 3rd Party Monitoring Dashboard

![3rd Party Monitoring](3rd%20Party%20%26%20Partner%20Monitoring.jpg)

**Purpose:** Monitor how leasing and insurance partners consume telematics data.

| Visual | Function |
|---|---|
| **3rd Party Mapping (treemap)** | Share of partners (Mandiri Utama Finance, CIMB Niaga Finance, ACC, BFI Finance, Adira Finance) |
| **Data Usage by Leasing** | Data consumption per leasing company |
| **Data Usage Leasing by Insurance** | Total customers per insurance partner |
| **Data Usage Leasing by Model** | Billing value per vehicle model |

**Business questions answered:** Which partners use telematics data the most? Which models generate the highest partner billing? Where are the opportunities for data monetization?


---

## 📁 Repository Structure

```
├── images/          # Dashboard screenshots
├── sql/             # SQL scripts for staging, modeling, and KPI logic
├── python/          # Data cleansing & transformation scripts
├── ssis/            # SSIS package documentation
├── denodo/          # Denodo view definitions
└── README.md
```
