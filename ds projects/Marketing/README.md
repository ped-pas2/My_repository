# Credit Card Customer Segmentation (8 → Optimal Segments)  

## Purpose  
This project segments credit card customers of a New York City bank into **8 initial clusters**, then refines them into **4–5 actionable groups** based on spending, payments, and credit behavior. The goal is to enable **hyper-targeted marketing** while balancing granularity and practicality.  

---

## Project Description  
The bank provided **6 months of transaction data**, including:  
- **Spending**: Purchases, cash advances, installment payments  
- **Credit Usage**: Balance, credit limits, utilization ratios  
- **Payment Behavior**: On-time payments, minimum vs. full payments  

Using **PCA + K-Means**, we:  
1. Identified 8 preliminary segments for fine-grained analysis.  
2. Merged similar clusters to create 4–5 high-impact groups.  
3. Recommended tailored strategies per segment.  

---

## Implementation Steps  

### 1. Data Preprocessing  
- Handled missing values (median imputation).  
- Scaled features (`StandardScaler`).  
- Applied **PCA** (retained **90% variance** for clustering).  

### 2. Initial Clustering (8 Segments)  
- Used **Elbow Method + Silhouette Analysis** → Optimal `K=8`.  
- Key metrics:  
  - **WCSS** (Within-Cluster Sum of Squares).  
  - **Cluster Separation Score**.  

### 3. Cluster Consolidation (4–5 Final Segments)  
- Merged clusters with overlapping behavior (e.g., low spenders + inactive users).  
- Validated using:  
  - **Business interpretability**.  
  - **Statistical significance** (ANOVA tests).  


## Identified Customer Segments
Based on transaction frequency analysis, we've identified 5 core customer segments:

| Segment               | Frequency | Profile              | Key Characteristics          |
|-----------------------|-----------|----------------------|------------------------------|
| BALANCE               | 272       | Mass Market          | Basic credit needs, low-risk  |
| CASH_ADVANCE         | 214       | Middle-Income        | Moderate spending            |
| CASH_ADVANCE_TRX    | 170       | Digital Natives      | Tech-savvy, mobile-focused   |
| PRC_FULL_PAYMENT      | 7         | High-Net-Worth       | Premium spending             |
| Small Business      | N/A       | Entrepreneurs        | High transaction volume      |

## Strategic Recommendations based on research..

### 🎯 BALANCE (Mass Market)
- **Offer**: No-frills credit cards with 1% cashback on essentials
- **APR**: Low introductory rates
- **Goal**: Retain high-volume customers

### 💳 CASH_ADVANCE (Middle-Income)
- **Offer**: 1.5% flat cashback cards
- **Perks**: Travel insurance
- **Goal**: Upsell to premium tiers

### 📱 CASH_ADVANCE_TRX (Digital Natives)
- **Offer**: App-integrated rewards
- **Features**: Mobile wallet bonuses
- **Goal**: Increase digital engagement

### ✨ PRC_FULL_PAYMENT (High-Net-Worth)
- **Offer**: Metal premium cards
- **Benefits**: Lounge access, concierge
- **Goal**: Deepen luxury loyalty

### 🏢 Small Business (Hypothetical)
- **Offer**: Business expense cards
- **Tools**: Spending analytics
- **Goal**: Capture B2B spending

**🛠 Tools Used**:
- Python 