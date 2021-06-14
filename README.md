# QATest_NewJoiner
Test for New Joiner 
Test challenge for POMELO QA Engineer


The Fashion Company Provide product delivery for there orders 
can take order online for clothes and Accessory .The delivery charges will be calculated depends on of 
-Number of Boxes.
-TodatPrice 
-Range(Distance)
-customer type
-Service chanrge

Customer will get discount if customer residence is within 10KM on 
Shop or if he order is more than 200 THB and more than 10KM will be calculated as usual

**
Index Formula**
Delivered vehicle type will be selected by calculating with number of order(Boxes).


POMELO WHEEL if index <40

GRABCAR if index >= 40

When


Clothe boxes = 1.3 Per box
accessory box = 1 per box

Cosider one box can have one product or multiple product charges will be on box not specific to product 

**Examples**


Order 20 x clothe boxes and 10 x accessory boxes

Index = (20 * 1.3) + 10 = 36

Then select 'POMELO WHEEL' for delivery


Order 20 x clothe boxes and 14 x accessory boxes

Index = (20 * 1.3) + 14 = 40

Then select 'GRABCAR' for delivery

Order 15 x clothe boxes and 20 x accessory boxes

Index = (15 * 1.3) + 20 = 39.5 then ROUNDUP to 40

Then select 'GRABCAR' for delivery

Delivery Charge Formula


**POMELO WHEEL**

Started at 10 THB

Distance between 0 - 30 Kilometers = 7.2 THB / Kilometers

Distance above 31 Kilometers = 14 THB / Kilometers

Delivery Charge will be included 10%


**GRABCAR**

Started at 20 THB

Every distance (1 rate) = 12 THB / Kilometers

Delivery Charge will be included 10%

Discount
If customer orders + Delivery fee >= 200 THB

Deliver charge will be deducted from distance between 0 - 15 kilometers

Deliver charge above 15 kilometers will be calculated as usual

If customer orders + Delivery fee < 200 THB

Deliver charge will be calculated as usual without discount offer


How logic works
**Example#1**

Order 20 x clothe boxes and 14 x accessory boxes

The price of Clothes boxes = 210 THB

Distance from store to Customer residene  = 20 kilometers

1. Index = 20 * 1.3 = 36

Then select POMELO WHEEL to delivery (POMELO WHEEL has the starter fee at $10)


2. Distance for 0 - 30 kilometers (20 kilometers)
Then 10 + (20 * 7.2) = 154 THB
Included service charged 10% = 154 * 1.10 = 169.4 ~ 170


3. Discount if the price >= 200 THB
Then 10 + (15 * 7.2) = 118 THB
Included service charged 10% = 118 * 1.10 = 129.8 ~ 130

Total Delivery charges = 170 - 130 = 40 THB

**Example#2
**
Ordered 20 x Meal Boxes and 14 x Dessert Boxes
Order 20 x clothe boxes and 14 x accessory boxes

The price of Meal and Dessert boxes = 500 THB

Distance from restaurant to destination = 20 kilometers
Distance from store to Customer residene  = 20 kilometers

1. Index = (20 * 1.3) + 14 = 40
Then select CAR to delivery (CAR has starter fee at 20THB)

2. Distance = 20 kilometers
Then 20 + (20 * 12) = 260THB
Included service charged 10% = 260 * 1.10 = 286

3. Discount if the price >= $200
Then 20 + (15 * 12) = 200 THB
Included service charged 10% = 200 * 1.10 = 210

Total Delivery charges = 286 - 210 = 76 THB
**Example#3**

Ordered 38 x Dessert Boxes
ordered 38 X acessory boxes

The price of Meal and Dessert boxes = 199 THB

Distance from restaurant to destination = 32 kilometers

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
