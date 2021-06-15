# QATest_NewJoiner

Test challenge for POMELO QA Engineer


The Fashion Company Provides product delivery for there orders 
can take order online for the Fashion clothes and  Fashion accessory .The delivery charges will be calculated depends on of 
-Number of Boxes.
-Total Price 
-Range(Distance)
-customer type
-Service chanrge

Customer will get discount if customer residence is within 15KM from
Pomelo Shop(Store) or if order price is more than 200 THB. and more than 15KM will be calculated as usual

************************************************************
**Index Formula****
Delivered Delivery type will be selected by calculating with number of orders(Boxes).


POMELO WHEEL if index < 40

GRABCAR if index >= 40

When

Fashion clothes = 1.3 Per box
Fashion accessory = 1 per box

Cosider one box can have one product or multiple product charges will be on box not specific to product 

**Examples**


Order  of 20 x Fashion clothes boxes and 10 x  Fashion accessory boxes

Index = (20 * 1.3) + (10*1) = 36

Then select 'POMELO WHEEL' for delivery


Order 20 x Fashion clothes and 14 x  Fashion accessory Boxes

Index = (20 * 1.3) + (14 *1) = 40

Then select 'GRABCAR' for delivery

Order 15 x Fashion clothes and 20 x  Fashion accessory boxes

Index = (15 * 1.3) + (20 *1) = 39.5 then ROUNDUP to 40

Then select 'GRABCAR' for delivery

******************************************
Delivery Charge Formula

**POMELO WHEEL**

Started at 10 THB

Distance between 0 - 30 Kilometers = 7.2 THB / Kilometers

Distance above 31 Kilometers = 14 THB / Kilometers

Delivery Charge will be included 10% Service charge


**GRABCAR**

Started at 20 THB

Every distance (1 rate) = 12 THB / Kilometers

Delivery Charge will be included 10% Service charge

**Discount**
If customer orders + Delivery fee >= 200 THB

Deliver charge will be deducted from distance between 0 - 15 kilometers

Deliver charge above 15 kilometers will be calculated as usual

If customer orders + Delivery fee < 200 THB

Deliver charge will be calculated as usual without discount offer

***************************************************************************************
How logic works
**Example#1**

Order 20 x Fashion clothes Boxes 

The price of Fashion clothes boxes = 210 THB

Distance from store to Customer residence  = 20 kilometers

1. Index = 20 * 1.3 = 36

Then select POMELO WHEEL to delivery (POMELO WHEEL has the starter fee at 10 THB)


2. Distance for 0 - 30 kilometers (for 20 kilometers)
Then 10 + (20 * 7.2) = 154 THB
Included service charged 10% = 154 * 1.10 = 169.4 ~ 170


3. Discount if the price >= 200 THB
Then 10 + (15 * 7.2) = 118 THB
Included service charged 10% = 118 * 1.10 = 129.8 ~ 130

Total Delivery charges = 170 - 130 = 40 THB

**Example#2
**
Ordered 20 x Fashion clothes Boxes and 14 x Fashion accessory Boxes 

The price of Fashion clothes and Fashion accessory Boxes = 500 THB

Distance from store to Customer residence  = 20 kilometers

1. Index = (20 * 1.3) + 14 = 40
Then select **GRABCAR** to delivery (GRABCAR has starter fee at 20THB)

2. Distance = 20 kilometers
Then 20 + (20 * 12) = 260THB
Included service charged 10% = 260 * 1.10 = 286

3. Discount if the price >= 200 THB
Then 20 + (15 * 12) = 200 THB
Included service charged 10% = 200 * 1.10 = 210

Total Delivery charges = 286 - 210 = 76 THB
**Example#3**

ordered 38 X Fashion accessory Boxes 

The price of Fashion clothes and Fashion accessory Boxes  = 199 THB

Distance from customer residence to store  = 32 kilometers

1. Index = 38
Then select POMELO WHEEL to delivery (POMELO WHEEL has starter fee at 10THB)

2.1 Distance for 0 - 30 kilometers (30 kilometers)
Then 30 * 7.2 = 216 THB

2.2 Distance for 31 - 32 kilometers (2 kilometers)
Then 2 * 14 = 28 THB

2.3 Include started fee = 10
Then 216 + 28 + 10 = 254 THB

2.4 Included service charged 10% 
Then 254 * 1.10 = 279.4 ~ 275

3. Discount if the price >= 200 THB
None
Total Delivery charges = 275 THB

As a QA engineering you need to test product delivery systeam  
 - Estimate time to Test 
 - Create test Scenarioes as details As possible 
 - Explain how to test or technique you use to create the test scenarios
