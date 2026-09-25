# Sales Analysis Project

## Business Context

This project analyzes retail sales data from a technology and multimedia chain operating in nine U.S. cities. The business goal is to identify the most effective times, locations, and product categories for promotional campaigns by understanding sales patterns from recent transactions.

The dataset contains one row per product in an order, with details such as the order identifier, product name, quantity sold, unit price, transaction date/time, and purchase address. These fields make it possible to study sales performance by time, location, and product group.

## Dataset

Overview of the raw file:

- 186,850 rows, of which 185,950 are valid transactions covering 178,437 distinct orders;
- orders dated from 1 January 2019 to 1 January 2020 (34 rows fall on 1 January 2020);
- sales in nine cities: San Francisco, Los Angeles, New York City, Boston, Atlanta, Dallas, Seattle, Portland and Austin. Portland includes both Portland, OR and Portland, ME, so city should be combined with state to tell them apart.

Initially, there are four product categories:

| Product category | Share |
| --- | ---: |
| USB-C Charging Cable | 12% |
| Lightning Charging Cable | 12% |
| AAA Batteries (4-pack) | 11% |
| Other | 65% |

## Research Questions

### Question 1: What information is already available in the problem statement? What important information is missing or ambiguous?

The problem statement gives us the context of the company (a technology and multimedia chain in nine U.S. cities) and what the manager wants: to find the best moments, locations and product groups for future campaigns. But a lot of information is missing. First, there are no product groups in the data (for example phones, headphones or cables), so we need to create them ourselves. Second, the word "best" is not clearly defined: we don't know if it means the products that generate the most revenue, the products that sell the most units, or something else.

### Question 2: Who are the stakeholders, what decisions do they need to make, and what would make the analysis useful to them?

The main stakeholder is the manager (and probably the marketing team). They need to decide when, where and on which products to run the next campaigns. To be useful, the analysis should clearly highlight the best product categories, the best locations and the best moments for sales, with simple results and charts that are easy to use for a decision.

### Question 3: Suggest a list of analytical questions that can be answered with the available variables. Identify the main variable or variables of interest for each question.

- Which product sells the most units? (Product, Quantity Ordered)
- Which product generates the most revenue (price × quantity)? (Product, Quantity Ordered, Price Each)
- What are the top 3 cities with the most items sold? (Purchase Address, Quantity Ordered)
- Which month and which hour of the day have the most sales? (Order Date, Quantity Ordered, Price Each)
- Which products are often bought together in the same order? (Order ID, Product)

### Question 4: Describe the expected type, measurement scale, and analytical role of every variable.

| Variable | Expected type or scale | Possible analytical role |
| --- | --- | --- |
| `Order ID` | Categorical identifier (nominal) | Links rows to the same transaction/order; allows aggregation at order level |
| `Product` | Categorical text (nominal) | Identifies the sold item and supports product-level performance analysis |
| `Quantity Ordered` | Numeric count (discrete, integer) | Measures sales volume and contributes to units sold and revenue calculations |
| `Price Each` | Numeric monetary value (continuous/ratio) | Used to compute revenue and average order value |
| `Order Date` | Date/time variable (datetime) | Enables trend analysis by day, week, month, hour, and seasonality |
| `Purchase Address` | Text / geospatial location (string + address) | Supports geographic analysis by city, state, or region and comparison of sales locations |

### Question 5: Based on your experience, which additional variables would improve the analysis? Explain how the retailer could collect them and whether they might raise privacy or ethical concerns.

- **Product group** (phone, headphones, cable, etc.): the retailer can add it easily from its product catalog. No privacy concern.
- **Age of the buyer**: it could be collected with a loyalty card or a customer account. This raises privacy concerns, so the customer must give consent and the data should be anonymised.
- **Product rating** (customer reviews): it could be collected after the purchase with an email or on the website. Low privacy risk, but reviews can be biased because only some customers answer.

## Main Findings

[Complete this section during the analysis.]

## Reproducing the Analysis

[Document the commands needed to recreate and run the project.]

## Best Pratice for git
- chore: set up or maintain the project without adding an analytical result;
- feat: add a new data-processing step, analysis, visualization, or result;
- fix: correct an error in the project or analysis;
- docs: change documentation only.

Example :
- feat(analysis): compare hourly sales