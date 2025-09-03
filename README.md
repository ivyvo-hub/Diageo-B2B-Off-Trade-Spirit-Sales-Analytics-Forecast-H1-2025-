# Diageo B2B Off Trade Spirit Sales Analytics and Forecast H1 2025
Table of Contents
1. [Project Background & Objective](#1-project-background--objective)  
2. [Data Source & Structure](#2-data-source--structure)  
3. [Executive Summary](#3-executive-summary)  
4. [Insights Deep-Dive](#4-insights-deep-dive)  
   4.1 [Diageo's H1 2025 Sales Performance](#diageos-h1-2025-sales-performance)  
   4.2 [Sales drivers](#sales-drivers)   
   4.3 [FY 2025 Sales Forecast](#fy-2025-sales-forecast)  
   4.4 [Sales Performance & Forecast Recap](#sales-performance--forecast-recap)  
5. [Closing the Gap: H2 2025 Priorities & Recommendation](#5-closing-the-gap-h2-2025-priorities--recommendation)  
   5.1 [What to push: Category/Variant strategy](#what-to-push-categoryvariant-strategy)  
   5.2 [Where to act: Store level strategy](#where-to-act-store-level-strategy)  
6. [Limitations & Next Steps](#6-limitations--next-steps)  
---
# **1. Project Background & Objective**

> _This project is based on publicly available data from the Iowa State Government. The business context, objectives, and strategies are fictional, created to demonstrate data analytics and decision-making capabilities._

Diageo, a global leader in spirits, is aiming to strengthen its position in North America—its largest market. Performance across states, however, varies due to regulatory and market structures. Iowa, with its control-state model, serves as a critical region for commercial execution.

Building on strong 2024 results, the Iowa Sales team has set an ambitious **5% YoY growth target** for FY2025 in the B2B off-trade channel. With the year now at its **midpoint**, this is the right moment to evaluate progress and adjust tactics.

This project delivers an **interactive sales dashboard** to support this frontline team beyond static reporting.

The analysis centers on one business question:  
**“Are we on track to reach our 5% growth target—and what actions should we take in the next six months to ensure we hit it?”**

Insights and recommendations are provided in the following areas:

**1. H1 Performance Assessment & H2 Forecast**:

A review of H1 2025 results and forward outlook, covering:
   - **Sales Size & Shape:** Total Revenue, Average order value and number of orders.
   - **Sales Drivers:** A breakdown of sales contribution by top Categories, Variants, Retail Partners, and Geographic Areas (Counties/Cities).
   - **Forward Outlook:** Baseline projection for H2 2025.

**2. Strategic Recommendations for H2:**

Actionable guidance for the Sales team, highlighting priority products, categories, and regions to focus resources and secure the 5% growth goal.

An interactive Power BI dashboard is available [here](https://app.powerbi.com/view?r=eyJrIjoiOTI3MTczZmYtYjFlZC00ZGQxLWE2NWYtNmE3NmI4NGI1MWZmIiwidCI6ImMxNmI5YjkzLTk4ZDUtNDNlOC1iNjc0LTg1ZjY3OWFkMzRjMyIsImMiOjEwfQ%3D%3D).
The Python queries for data cleaning is available [here](../Notebooks/01_Data_Ingestion_%26_Cleaning.ipynb).
The Python queries for exploratory analysis is available [here](../Notebooks/02_Exploratory_Data_Analysis.ipynb).

---
# 2. Data Source & Structure 

This project uses the **Iowa Department of Commerce’s open liquor sales dataset**, which records **retail-level (sell-out) transactions** under the state-controlled distribution model. In Iowa, all off-trade alcohol retailers must hold a liquor license, and every transaction is captured in the state’s commerce system. This ensures a complete and reliable view of actual spirits sell-out.

The dataset provides **transaction-level detail**, including product names, prices, quantities, and store locations across the state.

For this analysis, I focus on ~6 million Diageo transactions from 2023 to H1 2025 to evaluate YoY performance and assess H2 2025 growth opportunities.

The original dataset is published by the State of Iowa [here](https://data.iowa.gov/Sales-Distribution/Iowa-Liquor-Sales/m3tr-qhgy).

This project uses the **Iowa Liquor Sales dataset**, published by the Iowa Department of Commerce (Alcoholic Beverages Division).  

Due to GitHub's 100MB file size limit, the clean data file is stored externally. You can download them from the following link:  
[Download Clean Data (Google Drive)](https://drive.google.com/drive/folders/1ZRJAlXUiVSlFWLSQEbODIKitI3hKUYLV?usp=sharing)  

The Python queries for data cleaning is available [here](../Notebooks/02_Exploratory_Data_Analysis.ipynb).

---
# 3. Executive Summary

In H1 2025, Diageo Iowa generated **$26.8M revenue** from **177K orders** (AOV ~$152), down **–7.2% YoY** mainly due to order volume decline (–8.2%). At this pace, FY25 revenue is projected at **$62.8M**, leaving a **5% gap** to the +5% YoY growth target.

Two factors explain the shortfall:

- **Category dependence**: Whiskey (43% of sales) and Rum (13%) declines—driven by flagship variants _Crown Royal_ and _Captain Morgan_—outweigh gains in Tequila (+94.6% Don Julio Reposado) and RTD cocktails (+96.9%).
    
- **Store fragmentation**: No single geography drives losses; top stores contribute <5% each, with mixed performance even in hubs like Polk County.

**Recommendation**: Pursue a **dual strategy**—(1) protect Whiskey/Rum while accelerating Tequila, Vodka and RTD growth, **leveraging small-format packs** ; (2) drive execution through CLV–growth store segmentation to prioritize Champions, recover Loyal Giants, develop Rising Stars, and manage At-Risk accounts.

To complement this summary, I designed an interactive Power BI dashboard with three tabs: an Overview of H1 2025 performance (shown below), a Product Performance drilldown by category/variant, and a Store Performance segmentation by CLV and growth.

![Dashboard Overview](Images/0.%20Overall%20Performance%20Dashboard.png)

---
# 4. Insights Deep-Dive

## Diageo's H1 2025 Sales Performance

In H1 2025, Diageo generated approximately **$26.8M in revenue** from **177K orders**, with an **average order value (AOV) of ~$152**.  

Compared to H1 2024, revenue declined by **7.2% YoY**, driven primarily by an **8.2% drop in order volume**. The AOV remained broadly in line with last year, showing a slight **increase of 1.1%**, which indicates that the downturn was mainly due to weaker demand rather than smaller basket sizes.  

Monthly breakdown revealed consistent underperformance in most months, except March and a modest recovery in May. The sharpest YoY declines occurred in February and May (-16% to -17%), **again tied to lower order volume, not pricing shifts**.

![Diageo's H1 2025 Performance - Overall](Images/1.%20Diageo's%20H1%202025%20Performance%20-%20Overall.png)
![Diageo's H1 2025 Performance - By Month](Images/2.%20Diageo's%20H1%202025%20Performance%20-%20By%20Month.png)


### Sales drivers

#### Sales by Category/Variant

Diageo’s sales are **highly concentrated across a few categories and variants**:  
- **By Category:** Whiskey accounts for ~43% of total revenue. The next 3 categories each contribute 13–19%, bringing the top 4 categories to ~88% of total revenue.  
- **By Variant:** The top 5 variants generate ~40% of revenue, while the top 20 variants represent nearly 80% of H1 2025 revenue.  

This concentration means overall results are **heavily impacted by a few core categories and variants**. The decline in major categories such as **Whiskey (–12.9%)** and **Rum (–7.4%)**, alongside weaker performance in flagship variants like **Crown Royal (–4% to –6%)** and **Captain Morgan (–2% to –14%)**, played a central role in the YoY revenue decline.

There are, however, some positive signals. For example, **Don Julio Reposado grew +94.6%**, driving momentum in the **Tequila & Mezcal** category. The **Ready-to-Drink (RTD) portfolio** also posted solid growth of **+96.9%** from a small base, therefore, not sufficient to offset declines in core categories.

The next step is to break down performance by geography to pinpoint where the decline is concentrated.  

![Sales by Category and Variant](Images/3.%20Sales%20by%20Category%20and%20Variant.png)

#### Sales by County/City/Store

Geographically, revenue is partially concentrated in urban centers such as Des Moines (13.1%) and Polk County (23.3%), but outside of these, sales are decentralized across cities and counties.

At the store level, the landscape is highly fragmented. The top 2 stores account for only **4.4%** and **3.8%** of total revenue, while other stores each contribute less than 2%.  

Moreover, growth trends are inconsistent across all levels including counties, cities and stores:  
- **By County/City:** Some high-revenue markets declined—for example, **Des Moines in Polk County (–6.7%)**—while smaller markets such as **Dubuque grew (+12.8%)**.  
- **By Store:** Similar to the county level, top stores like **Hy-Vee #3 Des Moines (–9.5%)** and **Central City 2 (–6.9%)** recorded declines. Even within Dubuque - the growing county, overall growth was driven by a few outperforming stores, while many others in the area still contracted.  

Overall, the data indicates that the revenue decline is **broad-based across the state**. It is not concentrated in a single geography, but rather spread across multiple counties and stores.  

![Sales by County, City and Store](Images/4.%20Sales%20by%20County,%20City%20and%20Store.png)

### FY 2025 Sales Forecast

Diageo is forecasted to generate $35.9M in H2 2025. Combined with actual H1 results, total FY25 revenue is projected to reach $62.8M — just ~95% of the +5% YoY growth target.

There remains a ~5% shortfall, signaling the need for targeted commercial actions in H2 to close the gap and stay on track.

![H2 2025 Sales Forecast](Images/5.%20H2%202025%20Sales%20Forecast.png)

### Sales Performance & Forecast Recap

Diageo is projected to reach **$62.8M in FY25**, or ~95% of its +5% YoY growth target—leaving a ~5% shortfall.

Two key patterns explain the gap:

- **Variant concentration:** The top 20 variants drive ~80% of sales, with steep declines in **Whiskey (–12.9%)**, **Rum (–7.4%)**, and flagship brands like **Crown Royal** and **Captain Morgan**. Growth pockets (e.g., **Don Julio Reposado +94.6%**) remain too small to offset losses.
    
- **Geographic fragmentation:** While hubs like **Polk County (23.3%)** and **Des Moines (13.1%)** declined, sales are broadly spread across many counties and stores, each contributing small shares.

These insights highlight the need to focus on **core variants with outsized impact** while addressing performance **across a fragmented store base**. This sets the stage for the next section: how Diageo can close the gap in H2.

---
# 5. Closing the Gap: H2 2025 Priorities & Recommendation

To bridge the 5% shortfall and achieve the annual growth target, Diageo needs a dual focus on **Category/Variant strategy** (what to push) and **Store-level strategy** (where to act).

# What to push: Category/Variant strategy

When analyzing category/variant performance, two angles are critical:

1. **Market level** – Is the total category shrinking or growing? Which competitor variants are driving trends?
    
2. **Positioning level** – Where does each Diageo variant sit relative to competitors in terms of revenue and growth?

To support this, the Sales Dashboard (tab: _Product Performance_) provides a quadrant chart plotting each variant by **Revenue vs. YoY Growth**. Variants are grouped into four actionable clusters:

- **Star** – Large revenue share, growing
    
- **Emerging** – Small share, growing
    
- **Defend** – Large share, declining
    
- **De-prioritize** – Small share, declining

![Product Performance](Images/6.%20Product%20Performance.png)

Based on the data, we draw several insights at the category level. To keep this section concise, only key findings and supporting numbers are highlighted here. Full details can be explored directly in the **Product Performance** tab of the shared Dashboard.

| Category | Current Status | Recommendation for H2 2025 |
|----------|----------------|-----------------------------|
| **Whiskey** | Whiskey remains Diageo’s largest category, with Crown Royal at its core. Four flagship variants—Regal Apple, Original, Black Berry, and Peach—collectively contribute ~73% of Diageo’s Whiskey revenue. Yet all are declining, with YoY drops of –4% to –30%. The downturn is consistent across cities and stores, suggesting a network-wide issue.<br><br>The category itself contracted (–1.4% YoY), and many competitors are also under pressure. Still, a few rising stars stand out: **Fireball Cinnamon Whiskey mini (Sazerac) +14.4% YoY (3.2% share)**, **Jim Beam +8.6% YoY (2.8% share)**. These brands highlight selective momentum that could threaten Crown Royal’s position if left unchecked. | 1. **Core Protection – Defend the Crown Royal**: Prioritize Regal Apple and Original. Push shelf visibility (facings), consumer sampling, and in-store events.<br><br>2. **Competitive Defense – Counter Rising Stars**: Test Crown Royal minis/50ml trial packs in priority stores and re-emphasize Canadian whiskey differentiation vs. Bourbon (smoothness, mixability). |
| **Rum** | Diageo's Rum revenue is mainly driven by **Captain Morgan Original Spiced** across key formats—Original (–1.8%), Barrel (–14%), PET (–15.7%)—together ~40% of segment revenue. Smaller variants like **Captain Morgan Mini (+1.3%)** grew slightly but remain minor. Decline is statewide, not local.<br><br>The overall Rum category declined –2.8% YoY. Most top variants under pressure; growth variants too small to offset broader decline. | 1. **Defend Core – Captain Morgan Original Spiced**: Prioritize facings and seasonal activations.<br><br>2. **Micro-Growth Bet (minis)**: Push minis in high-velocity stores (80% revenue cohort). |
| **Tequila & Mezcal** | Growth in 2025 was **driven by Don Julio Reposado (+94.6% YoY)**, now #2 by share (7.1% of category, ~30% of Diageo’s Tequila). Additional momentum from Don Julio Anejo (+15.7%), Reposado Mini (+201.7%), Astral variants (triple-digit growth off small base).<br><br>Not all flagships sustained growth: **Don Julio Blanco (–9%)**, **70th Anniversary (–17.8%)**, **Casamigos Blanco (–29.6%)**, **Casamigos Reposado (–35.8%)** together lost $278K. Decline is market-wide.<br><br>Competitors also weakened: **Patron Silver (–16.9%)**, **Jose Cuervo variants (–6% to –13%)**, creating openings in premium and small-format segments. | 1. **Double Down on Don Julio Reposado (Hero SKU)**: Boost facings & visibility in premium shelves.<br><br>2. **Leverage Format Momentum (Minis)**: Expand mini distribution in top stores.<br><br>3. **Stabilize Laggards**: Reposition Casamigos as “accessible premium” to reduce cannibalization.<br><br>4. **Exploit Competitor Weakness**: Equip reps with “switch playbooks” to recommend Don Julio in accounts overstocked on Patron Silver.<br><br>5. **Test Astral as Challenger Brand**: Run pilot push in 1–2 counties. |
| **Vodka** | Vodka grew +1.8% YoY. **Smirnoff 80Prf PET** is top-selling (27.1% of Diageo’s vodka, +12.3% YoY). In contrast, standard 80Prf declined –5.1%, suggesting consumer shift to PET packaging/value tier.<br><br>Flavored Vodka mixed: **Vanilla (+35%)**, **Strawberry (+12%)** rising from small base; **Red, White & Berry** and **Caramel** declined. Shifts not geography-specific.<br><br>Competitively, **Tito’s Handmade Vodka** (32.8% share) declined –2.9% YoY. | 1. **Double Down on PET Pack Advantage**: Ensure PET pack wide distribution in top 200 stores; position as lead SKU.<br><br>2. **Reallocate Flavor Portfolio**: Push Vanilla & Strawberry with seasonal campaigns; deprioritize Caramel and Red, White & Berry. |
| **Ready to Drink (RTD) Cocktail** | Strong 2025 traction: **Bulleit Old Fashioned (+54%)**, **Ketel One Espresso Martini (+195%)**. New **Crown Royal Whisky Sour Black Cherry** contributed 13% of RTD volume. Legacy **Captain Morgan Long Island Iced Tea (–9.6%)** underperformed.<br><br>Category dominated by **Jose Cuervo** but signs of fatigue: Authentic Lime Margarita (–14.8%), Strawberry Lime Margarita (–7.8%), Golden Margarita (+2.1%).<br><br>**Sazerac’s Buzzballz** launches rapidly gained share: Berry Cherry Limeade (5.1%), Biggies Tequila Rita (2.8%).<br><br>6 of top 10 SKUs are Margarita-style, underscoring consumer preference. Opportunity to expand Diageo’s Margarita RTD line. | 1. **Double Down on Premium Cocktail Experiences**: Scale Bulleit Old Fashioned & Ketel One Espresso Martini; position as premium trade-up vs. cheaper RTDs.<br><br>2. **Expand into Margarita Space**: With Jose Cuervo weakening and 6/10 top SKUs Margarita-based, push Astral/Don Julio Margarita RTDs to steal share.



### Where to act: Store level strategy

While category priorities set the **growth formula**, execution depends on stores—where performance is fragmented and uneven. Segmenting stores by **Customer Lifetime Value (CLV)** and **YoY growth** helps identify where to **defend, accelerate, or re-engage**.

#### Store Segmentation Framework

- **Champions (High CLV, High Growth)** → Core growth engines; protect and scale.
    
- **Loyal Giants (High CLV, Declining Growth)** → Anchor stores; defend revenue base.
    
- **Rising Stars (Low CLV, High Growth)** → Emerging growth points; nurture and test.
    
- **At-Risk Accounts (Low CLV, Declining Growth)** → Low priority; selective intervention.

Full segmentation details are available in the _Store Performance_ tab of the dashboard.

![Store Performance](Images/7.%20Store%20Performance.png)

Building on this framework, my recommendations for each segment are as follows:

| Store Segment | Current Status | Recommendation for H2 2025 |
|---------------|----------------|-----------------------------|
| **Champions (High CLV, Strong Growth)** | +17.5% YoY<br>Diageo strong (21% share). Growth led by **Crown Royal Regal Apple (+19%)**, **Don Julio Reposado (+242%)**, **Captain Morgan Spiced (+22%)**. | - **Reinforce premium trends**: Push **Don Julio and RTD premium cocktails**; use these stores as pilots for premium launches.<br><br>- **Maximize PET packaging (Smirnoff, Crown Royal)** to match consumer shift to value + convenience.<br><br>- Treat as **innovation playgrounds**: test flavor extensions (e.g., flavored whiskey RTDs). |
| **Loyal Giants (High CLV, Declining Growth)** | –12.6% YoY<br>Very important (63% of revenue). Flagship Diageo variants declining: **Crown Royal –12.7%, Regal Apple –15.4%, Captain Morgan –10%**. Competitors (Tito’s, Black Velvet, Fireball) also down. | - **Defend the base**: Drive **Crown Royal recovery** (Original + Apple) via **displays, price-packs, promotions**.<br><br>- **Counter Tito’s dominance**: Push **Smirnoff PET + flavored vodka** as trade-up/trade-across options.<br><br>- **Stop share leakage**: Position **Don Julio Reposado + Anejo** to capture premium Tequila trade-up that Tito’s misses. |
| **Rising Stars (Low CLV, Fast Growth)** | +57% YoY<br>Small contribution (4.5%) but rapid growth in **Fireball (+53%)**, **Regal Apple (+41%)**, **Captain Morgan Spiced (+48%)**, **Smirnoff 80Prf PET (+66%)**. | - **Invest selectively**: Expand **distribution of fast movers** (Captain Morgan, Fireball, Smirnoff PET).<br><br>- **Experiment with single-serve/small formats** (mini bottles, Buzzballz-style RTDs).<br><br>- Treat as **incubator stores** for new flavors/formats before statewide rollout. |
| **At-Risk Accounts (Low CLV, Negative Growth)** | –33.3% YoY<br>Declines across all Diageo variants (**Crown Royal –34%, Regal Apple –28%, Captain Morgan –20%**). Competitors (Tito’s, Fireball, Black Velvet) also down double digits. | - **Triage approach**: Focus only on retailers with **Tequila/RTD growth potential**.<br><br>- **Bundle strategy**: Use value packs (Smirnoff PET, Captain Morgan promos) to avoid delistings.<br><br>- **Category defense**: Pitch **Don Julio + RTDs** as higher-margin alternatives instead of pushing declining Crown Royal SKUs.

---
# 6. Limitations & Next Steps

While this analysis provides a clear direction, a few constraints should be acknowledged:

- **Data Coverage:** The scope is limited to sales transactions in Iowa’s off-trade spirits channel. It excludes marketing spend, competitor promotions, and shelf placement, all of which can materially influence performance. Profitability data (margin) is also missing, so recommendations are oriented toward **top-line growth**. Coordination with Finance and Trade teams is necessary before execution.
    
- **Forecasting Assumptions:** Projections rely on historical sales trends and do not fully capture disruptive events or significant competitive moves.

**Next Steps**  
Future iterations should connect sales performance with specific marketing and trade activities to measure ROI and optimize investments. Expanding the dataset to include profitability, demographics, and competitor activity would enhance the quality of insights and support sharper strategic recommendations.
