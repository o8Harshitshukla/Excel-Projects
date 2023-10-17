# E-commerce Order Analysis and Verification

## Project Overview

Welcome to the E-commerce Order Analysis and Verification project, developed for an Indian e-commerce company referred to as "X." This project focuses on ensuring the accuracy of charges levied by courier partners for the thousands of daily orders processed by X.

## Business Scenario

X collaborates with multiple courier companies for order deliveries, and these companies charge X based on two main factors: the weight of the products in the order and the distance between X's warehouse (pickup location) and the customer's delivery address (destination location). Given that X ships around 100,000 orders per month, it's essential to verify the accuracy of these charges to control monthly expenses.

## Data Sources

### Left-Hand Side (LHS) Data (X's internal data)

1. **Website Order Report**: Contains Order IDs and product details for each order. The Order ID links X's order data to the courier company's invoice.

2. **SKU Master**: Provides the gross weight of each product, used to calculate total shipment weight and compare it with the courier company's data.

3. **Warehouse Pincode to All India Pincode Mapping**: Determines delivery zones and aids in verifying courier company data against X's records.

### Right-Hand Side (RHS) Data (courier company invoice)

The courier company's invoice, in CSV format, includes:

- **AWB Number** (courier company's internal ID)
- **Order ID** (X's order ID)
- **Weight of shipment**
- **Warehouse pickup pincode**
- **Customer delivery pincode**
- **Zone of delivery**
- **Charges per shipment**
- **Type of shipment**

## Verification Process

1. **Data Integration**: Combine and merge LHS data to create a comprehensive dataset.

2. **Data Cleaning and Preprocessing**: Prepare the data for analysis, ensuring consistency and uniformity.

3. **Data Matching**: Match LHS and RHS data using the Order ID.

4. **Weight Calculation**: Calculate total shipment weight according to courier company weight slabs.

5. **Delivery Zone Determination**: Use the Pincode Mapping to determine delivery zones and compare with the courier company's zone data.

6. **Charge Verification**: Calculate expected charges based on total weight and delivery zone, cross-referencing with the courier company's rate card.

7. **Compare Charges**: Check for discrepancies between calculated and invoiced charges.

8. **Discrepancy Handling**: Investigate and document reasons for discrepancies.

9. **Reporting**: Create detailed reports with findings and recommendations for corrections or negotiations with the courier company.

## Conclusion

Regularly conducting this analysis and verification process helps X ensure accurate charges from courier partners, potentially saving costs and improving the company's financial management.

Feel free to explore the project repository for code and additional resources.

Output Data 1
The goal is to create a resultant CSV file with the following columns:
![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/f6d8e8e1-47b6-4599-a5a1-8126973316ee)



Output Data 2
Create a summary table


![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/b61d087c-9cd9-4712-8de8-a6be5ab8c2fb)


