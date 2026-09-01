# Project Overview
The Pizza Store Sales Analytics Dashboard is an end-to-end Data Analytics and Business Intelligence (BI) web application designed to analyze retail performance, customer ordering trends, and product mix. Built using a full Python analytics stack, MySQL, and Streamlit, it transforms multi-table relational sales data into actionable, interactive insights.

# Key Architectural & Technical Features

Database Querying & Data Pipeline: Connects dynamically to a local MySQL relational database (pizza_store) on port using pymysql. Executes complex SQL JOIN queries across four core tables—order_Wise_details, pizza_sales, pizza_wise_details, and pizza_order—to reconstruct complete transactional records.

Data Preprocessing & Cleaning: Utilizes Pandas to clean raw query results. Cleans duplicate join columns using iloc indexing, applies defensive type casting on numeric price and quantity metrics via pd.to_numeric(), and merges separate date and time fields into unified datetime objects (full_date) for granular time-series analysis.

Interactive Visualization (Plotly): Visualizes key business metrics inside a sleek dark UI theme (plotly_dark). Interactive charts track hourly order volume distributions (full_date.dt.hour), daily revenue trends (full_date.dt.day), top-selling order dates, and volume performance across pizza sizes (S, M, L, XL).

Dynamic Frontend & UI Engine (Streamlit): Leverages Streamlit to rapidly build a reactive, Python-native web application without requiring traditional HTML/JavaScript frontends. Customized using custom CSS injection to render an interactive dark layout with distinct visual containers, high-contrast KPI metric cards, and clean typography.

Interactive Filtering & Session Control (Streamlit): Integrates interactive sidebar widgets—such as multi-select dropdowns for pizza_category and min_pizza_size—enabling real-time, dynamic data slicing and instantaneous chart updates across the dashboard.

# Business Impact
By centralizing key performance indicators—such as total revenue, unique order counts (order_id.nunique()), average order values, and quantity metrics—the dashboard allows store managers to optimize inventory based on size popularity, streamline kitchen staffing around peak ordering hours, and identify high-revenue menu items.

# Dashboard Overview
![Pizza_Store_Analysis](Pizza_Store_Analytics- Dashboard.png)

Performance Optimization (Streamlit Caching): Implements Streamlit decorators (@st.cache_resource for database connection pooling and @st.cache_data for dataframe caching) to prevent redundant SQL queries, minimize reruns, and lower latency.
