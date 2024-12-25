# Accurate User Database and Training Resource Optimization

**In Partnership with Accenture**

## Introduction
Accenture collaborated with one of its federal clients to optimize a global supply chain system. This system, which tracks procurement, distribution, maintenance, and retirement of assets, contains over 10 years of data. Users in the system are assigned roles based on their functional responsibilities.

The objective of this project is to develop a **location-based dashboard** that identifies users requiring training, the training areas needed, and prioritizes these based on urgency.

---

## Datasets
- **`gmu_training_receiving`**: Users who received assets.
- **`gmu_training_location`**: Users who moved assets to new locations.
- **`gmu_training_disposal`**: Users who disposed of assets.

---

## Preprocessing and Modeling

### 1. **Training Disposals**
- Removed duplicates.
- Changed data types.
- Imputed missing data.
- Created additional columns using calculations from existing ones.
- Removed unnecessary columns.
- Performed mathematical calculations to assign weights for disposal roles.
- Standardized the `error_cost` column using `StandardScaler`.
- Normalized features using `MinMaxScaler`.
- Merged the original `total_cost` for reference.
- Outer joined tables:
  - **Top 10 highest scoring users**.
  - **Original total cost and results tables** (common field: `user`).
- Removed duplicate rows.
- Generated a new dashboard:
  - Renamed columns.
  - Displayed results sorted by score (descending).
  - Filtered records with `rating >= 0`.

### 2. **Training Locations**
- Checked and imputed missing values.
- Removed duplicate rows and unwanted punctuations.
- Corrected data types.
- Imputed `NaN` values with `0`.
- Created a new table for modeling.
- Assigned weights to location-related columns.
- Standardized the `role_location` column using `StandardScaler`.
- Normalized all features with `MinMaxScaler`.
- Merged the original `total_cost` for reference.
- Displayed results in descending order:
  - **Top 10 users with the highest scores**.
- Outer joined tables (common field: `user`).
- Removed missing values and duplicate rows.
- Generated a new dashboard with adjusted column names.

### 3. **Training Receiving**
- Checked for missing values and imputed with `0`.
- Removed duplicate rows and unwanted punctuations.
- Fixed data types.
- Assigned weights to the receiving role.
- Standardized the `error_cost` column using `StandardScaler`.
- Normalized other features with `MinMaxScaler`.
- Displayed results in descending order:
  - **Top 10 users with the highest scores**.
- Outer joined tables (common field: `user`).
- Generated a new dashboard with renamed columns.

---

## Final Data Integration
- Outer joined all three tables (common field: `user`).
- Handled missing values to indicate absence of specific roles.
- Calculated `total_rating`:
  - Displayed top 10 users by total score.
  - Indicated role presence (value = `1` for assigned roles).
  - Displayed top 10 locations for roles: disposal, location, and receiving.
- Exported final table to S3 for dashboard creation.

---

## Visualizations
### User Analysis
- **Users vs Total Rating** - Scatter plot.
- **Top 10 Users (Total Rating)** - Bar plot.
- **Top 10 Users (Disposal Rating)** - Bar plot.
- **Top 10 Users (Error Cost)** - Bar plot.

### Disposal Role Analysis
- **Top 10 Users (Error Actions by Scan Type)** - Bar plot.
- **Top 10 Users (Error Actions by Retirement Date)** - Bar plot.
- **Top 10 Users (Error Actions by Documentation)** - Bar plot.

### Location Role Analysis
- **Top 10 Users (Location Rating)** - Bar plot.
- **Top 10 Users (Error Cost)** - Bar plot.
- **Top 10 Users (Error Actions by Validation)** - Bar plot.

### Receiving Role Analysis
- **Top 10 Users (Receiving Rating)** - Bar plot.
- **Top 10 Users (Error Cost)** - Bar plot.
- **Top 10 Users (Error Actions by Misclassification)** - Bar plot.
- **Top 10 Users (Error Actions by Creation Method)** - Bar plot.

### Business Unit Analysis
- **Top 10 Business Units by Rating (Various Criteria)**:
  - Disposal Rating.
  - Scan Type Rating.
  - Retirement Date Rating.
  - Documentation Rating.
  - Error Cost Rating.
  - Location Rating.
  - Receiving Rating.
  - Misclassification Rating.
  - Creation Method Rating.

---

## Output and Deployment
- All processed data was exported to **Amazon S3** for integration into the dashboard.
- The dashboard enables actionable insights:
  - Identifies users requiring training.
  - Prioritizes training needs by urgency and location.
  - Displays top-performing users and error trends.

---

## Conclusion
This project showcases a streamlined approach to optimizing user training resources using robust data preprocessing, feature engineering, and visualization techniques. The dashboards provide valuable insights, enhancing operational efficiency and decision-making.

---
