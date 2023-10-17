**E-commerce Order Analysis and Verification Process:**

**Business Scenario:**

Imagine you work as a data analyst for an e-commerce company in India, referred to as "X." X handles a high volume of daily orders through its website and collaborates with multiple courier companies for order deliveries. These courier companies charge X based on two factors: the weight of the products in the order and the distance between X's warehouse (pickup location) and the customer's delivery address (destination location). On average, the delivery charge per shipment is around Rs. 100. With approximately 100,000 monthly orders, X incurs substantial expenses, necessitating accurate verification of charges levied by their courier partners.

**Input Data:**

**Left-Hand Side (LHS) Data (X's internal data spread across three reports):**

1. **Website Order Report:** Contains Order IDs and details of the products (SKUs) in each order. The Order ID serves as the link between X's order data and the courier company's invoice.

2. **SKU Master:** Provides the gross weight of each product, which is used to calculate the total weight of each order and compare it with the weight reported by the courier company in their CSV invoice. The courier company calculates weight in slabs of 0.5 KG multiples, so determining the total shipment weight and applicable weight slabs is necessary.

3. **Warehouse Pincode to All India Pincode Mapping:** This mapping helps determine the delivery zone (a/b/c/d/e) and enables comparison with the information reported by the courier company in their CSV invoice for each Order ID.

**Right-Hand Side (RHS) Data (courier company invoice in CSV format):**

The courier company's invoice in CSV format includes:

- **AWB Number (courier company's internal ID)
- **Order ID** (X's order ID)
- **Weight of shipment**
- **Warehouse pickup pincode**
- **Customer delivery pincode**
- **Zone of delivery**
- **Charges per shipment**
- **Type of shipment**

The invoice also outlines the courier charges rate card at the weight slab and pincode level. The type of shipment (Forward charges or Forward and RTO charges) determines the applicable charges based on zones and fixed and additional weights as per weight slabs. For the first 0.5 KG, a "fixed" rate applies, and for each additional 0.5 KG, an "additional" weight charge in the same proportion applies. The total charges comprise the sum of the "fixed" and "total additional" charges, if any.
Output Data 1
The goal is to create a resultant CSV file with the following columns:
![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/f6d8e8e1-47b6-4599-a5a1-8126973316ee)



Output Data 2
Create a summary table


![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/b61d087c-9cd9-4712-8de8-a6be5ab8c2fb)


