# Sales-Insight-Data-Analysis.

Problem Statement:

AtliQ Hardware is a company which supplies computer hardware and peripherals to many of their clients. And AtliQ Hardware has head office in delhi. They also have lot of regional offices throughout the India.
Bhavin Patel is the sales director in this company and he's facing lot of challenges. He is facing issues in terms of tracking the sales of AtliQ Hardware in this dynamically growing market.

So, as a data analytics team member, we need to provide the insights like revenue, sales quantity, profit, profit margin, top customers, top markets, revenue trend etc..to Bhavin Patel about his business.

### Steps followed 

- Step 1 :  MySql Workbench 

	
  
  1. Launch the workbench
	2.Create new MySql connection .
	In "Schemas"  there      will be a default schema called "SYS" .
	3. import the data
 
-Step 2 :  Data cleaning and ETL :


	Part 1 : Data Modeling

 		1.Load data into Power BI Desktop, dataset is the Mysql Database.
		2. Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.

		3. From MySql.
		4. give  names of server and Database .
 		server would be "localhost" and DB name "Sales".
		5. load the Data. 
		6. Establish the relationship between Tables by navigating to "Data Model" section .(Drag and drop the fields).
		STAR SCHEMA .
		7.Transfrom Data (ETL).


Part 2 : Data Transformation using "Power Query Editor"

	1. Go to markets Table. -->  Filter rows to delete "blank" values.
	2. Check how many values are "<=0" and filter out those values from transaction table.
	3. Convert the values in "USD" to "INR" in transactions table.
	4. keep only INR\r values and USD\Cr values.
	5. create conditional column and apply formula.
	6. After transformation close and load .
	7. Close and load.

Part 3 : Start Building our Dashboard

	1. Go to powerBi Dashboard and in "Home" click on  "Enter Data ". 
	2. Give Table a name as "BaseMeasures" --> Load
	"Base Measures " is used to plot different UI elements on our Dashboard.
	3. Create a Measure named "Revenue" and give it a formula to calculate total revenue.
	4. Create another measure called "Sales Quantity".

	5. Drag and drop those measures to dasboard to create a visual .
	
	
![image](https://github.com/user-attachments/assets/f5456f08-1f46-4833-90f4-c03f23ef7aae)




	7. create the slicer with value "year" in sales date.  
	8. create the slicer with value "cy_date" in sales date.  

 ![image](https://github.com/user-attachments/assets/9b65055c-d723-4a4e-b9cc-1f1ac3a090ec)


	9.Change Revenue by customers to Revenue by Markets.

DB CONTAINING Cost price , profit margin and profit margin % :
	1. Create a Measure 
	Total profit margin = SUM('sales transactions' [Profit_margin])

	2. Place a card and then drag and drop the Measure created.

	3.  Create another measure 
	Profit margin % = DIVIDE([Total profit margin] , [ Revenue] , 0) 

	4. Create another measure :
	Profit margin contribution % =DIVIDE([Total profit margin],CALCULATE( [Total profit margin] , ALL( ' sales products') , ALL( 'sales customers ' ) , ALL ( ' sales market ')))

	*** Make  it "%" in both steps 3 & 4.


	5. Revenue Contribution %
        	5.1 Create new measure 
Revenue Contribution % = DIVIDE([Revenue] , CALCULATE( [Revenue] , ALL( ' sales products') , ALL( 'sales customers ' ) , ALL ( ' sales market ')))


 	
	6. Create a Table Visual and give values :
         	a. Customer_name
	 	b. Revenue  
	 	c. Revenue contribution % 
	 	d. Profit Margin Contribution %
	 	e. Profit margin %

   ![image](https://github.com/user-attachments/assets/cd511ce2-7af6-460e-904f-adaff6664d41)


   ![image](https://github.com/user-attachments/assets/2f3c73d2-403a-438c-90ea-7e7a5e3fdbdd)

   ![image](https://github.com/user-attachments/assets/5353814d-8e55-4f6d-848d-34c0f8fcf922)


  
![image](https://github.com/user-attachments/assets/3ec1ca3e-7010-4fc3-a208-66f953dbf26c)








Multiple page report :

	1. Placed a button with title "Detailed analysis"
	2. on-click it will redirect you to Detailed navigation page where we created analysis report of Revenue ,profit margin percentage and profit contribution percentage based on Zones.

 ![image](https://github.com/user-attachments/assets/01f97afe-b406-4b1b-b0d2-19a6617f4870)


   

