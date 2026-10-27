# Smart Agriculture Database System – Crop & Disease Monitoring
### A College Database Management System (DBMS) Project

An enterprise-grade, responsive, full-stack Agricultural Database Management System designed for agricultural departments, farmers, and research administrators. Built with a predominantly **clean white interface**, accented with **Green (#22C55E)**, **Blue (#3B82F6)**, **Pink (#EC4899)**, **Black (#111827)**, and **Light Gray (#F3F4F6)**.

---

## 🌾 Project Overview & Key Features

1. **Crop Management**: Complete CRUD operations, tracking Crop Name, Variety, Planting/Harvest dates, Cultivated Area, Soil Type, Irrigation Method, Growth Stage, and Health Status.
2. **Crop Disease Monitoring**: Clinical disease detection log with symptoms, severity ratings (Low, Moderate, High, Critical with Pink alerts), affected coverage percentage, observations, expert recommendations, and resolution tracking.
3. **Farming Activities**: Comprehensive timeline of field operations (Soil Prep, Sowing, Irrigation, Fertilizer Application, Weeding, Pest Monitoring, Disease Treatment, Harvesting) with labor metrics and expenditures.
4. **Agricultural Resource Inventory**: Real-time inventory of seeds, fertilizers, manure, irrigation components, and agrochemicals. Automatic stock deduction and transactional consistency when usage is logged.
5. **Farmer Administration**: Administrator portal to supervise registered farmers, individual crop portfolios, disease incidents, and account statuses.
6. **Relational Analytics Dashboard**: 10 interactive charts powered by SQL aggregate queries (COUNT, SUM, AVG, GROUP BY):
   - Crop Distribution by Category (Doughnut)
   - Crop Growth Stage Distribution (Bar)
   - Disease Reports by Month (Line)
   - Disease Severity Distribution (Doughnut)
   - Most Frequently Reported Diseases (Bar)
   - Crop Health Status Overview (Doughnut)
   - Farming Activities by Type (Bar)
   - Resource Usage Analysis (Bar)
   - Monthly Farming Expenses (Area/Line)
   - Upcoming Harvest Schedule (Bar)
7. **Reports & CSV Export**: 8 exportable reports with date filters, search, and dynamic CSV downloads.
8. **Interactive DBMS Workbench**: Live in-app SQL Studio allowing evaluators and professors to execute SQL queries, examine the relational schema, and review normalization proofs (1NF, 2NF, 3NF).

---

## 🗄️ Database Architecture & Normalization

The database is normalized up to **Third Normal Form (3NF)**:
- `Users`: Central authentication and role-based permissions (`admin`, `farmer`).
- `Farmers`: Farm profile metadata linked 1:1 with `Users`.
- `Crops`: Cultivated crops linked 1:N with `Farmers`.
- `DiseaseReports`: Pathology logs linked 1:N with `Crops`.
- `FarmingActivities`: Operational schedules and expenses linked 1:N with `Crops`.
- `Resources`: Farm supplies owned by `Farmers`.
- `ResourceUsage`: Associative entity resolving M:N relationship between `Resources` and `Crops`.

### SQL Scripts Included in `/database/`:
- `schema.sql`: Complete DDL with Primary Keys, Foreign Keys, cascading actions, CHECK constraints, and B-tree indexes.
- `sample_data.sql`: Realistic seed records (10+ Farmers, 16 Crops, 21 Disease Reports, 27 Farming Activities, 16 Resources, 12 Usage records).
- `views.sql`: 5 reusable reporting views (`v_crop_health_summary`, `v_active_disease_alerts`, etc.).
- `dbms_queries.sql`: Advanced queries demonstrating JOINs, subqueries, GROUP BY with HAVING, and stored procedure with ACID transaction rollback.

---

## 🚀 Local Installation & Execution

### Prerequisites:
- Node.js (v18 or higher)
- MySQL Server (v8.0+)
- npm or yarn

### 1. Database Setup in MySQL:
```bash
mysql -u root -p < database/schema.sql
mysql -u root -p < database/sample_data.sql
mysql -u root -p < database/views.sql
```

### 2. Frontend & Backend Setup:
```bash
# Clone the repository and enter directory
cd smart-agriculture-system

# Install dependencies
npm install

# Run the development server (runs both frontend and dev tools on port 3000)
npm run dev
```

### 3. Demo Credentials:
- **Administrator**: `admin@smartagri.org` (Full admin privileges)
- **Farmer 1**: `ramesh.patel@farmmail.com` (Nashik, Maharashtra)
- **Farmer 2**: `anita.sharma@greenfields.in` (Karnal, Haryana)
- **Farmer 3**: `rajesh.kumar@agrilink.in` (Thanjavur, Tamil Nadu)
*(Or click any 1-Click Login button on the Login page for instant demonstration)*
