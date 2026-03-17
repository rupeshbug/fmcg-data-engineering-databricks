## Solving a post-merger data integration problem.

### Core challenges:

- Schema mismatch (ERP vs messy startup data)
- Data inconsistency (conflicting sales numbers)
- Missing data
- Different reporting cycles
- Scalability concerns

“Building a unified, reliable analytics layer from messy + structured sources.”

We will have data for both companies. We'll see things like:

- Different table names for similar data (e.g., sales_data vs orders)
- Different column names (cust_id vs customer_id)
- Different structures (one normalized, one flat)
- Missing or extra fields

### 1. Bronze Layer (Raw ingestion)

Ask yourself:

- Where is data coming from? (S3, CSVs, etc.)
- Are we preserving raw data as-is?
- How do we handle missing months / bad files?

👉 In our case:

- ERP data = clean, structured
- Sports Bar = messy (spreadsheets, exports)

### 2. Silver Layer (Cleaning + Standardization)

This is where the real value is.

Key questions:

- How do we align schemas?

- How do we standardize:

    - date formats
    - product names
    - units (kg vs pieces, etc.)

- What do we do with missing data?

👉 This is where we solve:

“Nothing ties together”

### Gold Layer (Business-ready data)

Now we're thinking like the COO:

- Total sales across both companies
- Inventory trends
- Forecast-ready datasets

Unified KPIs

👉 This directly maps to:

“One single reliable dashboard”

### Note: 

“I unified heterogeneous datasets from an ERP system and a startup by standardizing schemas, aligning business entities, and building a consistent data model in the Silver layer.”

Whenever there is differences, ask:

“How do I make these two datasets look like they came from the same system?”
