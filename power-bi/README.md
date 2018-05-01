# MarkLogic and PowerBI

This README is for the hands-on portion of the MarkLogic and PowerBI On Demand tutorial from MarkLogic University. 

## Requirements
To follow along with the video tutorial, you will need the following.

* MarkLogic 9 installed and running <http://developer.marklogic.com/products>.
* The MarkLogic 9 ODBC client driver <http://developer.marklogic.com/products/odbc>.
* PowerBI Desktop <https://powerbi.microsoft.com>.

## Instructions

1. Clone or download the `power-bi` MarkLogic University repository to your local machine.  
	You should have a folder with this structure:  
	
	* `\bi-tools\powerbi\marklogic_powerbi_tutorial\data\*.csv` files
	* `\bi-tools\marklogic_powerbi_tutorial\config\*.txt` files
	* `\bi-tools\marklogic_powerbi_tutorial\workspace\MarkLogic with PowerBI.xml` file

2. Import the workspace in Query Console.  
This workspace is composed of:
	
	* three tabs that will help us create a TDE template for the orders, people and returns data.
	* three tabs with mlcp instructions to import our orders, people and returns data to a database.
	* two tabs that will help us check that our views were created successfully and that there are populated with the Global Super Store data.
	* one tab that will create an ODBC application server to allow us to communicate with our Documents database through the MarkLogic ODBC driver.

3. Create TDE templates which define our views.  
Run the scripts from the following workspace tabs:

	* `insert orders template`
	* `insert people template`
	* `insert returns template`
	
	The templates will automatically be saved to the Schemas database used by Documents database. For simplicity, we are using the out of the box Documents database to load our data.  

	Explore the schemas database to check that our templates where inserted. To learn more about TDE, watch the Using Template Driven Extraction video tutorial on <https://mlu.marklogic.com/ondemand>.

4. Load data.  
	If you are getting started with MLCP, please read the getting started with MLCP at https://docs.marklogic.com/guide/mlcp/getting-started.
	
	Once the MLCP bin directory has been added to your PATH, open a new a command line, make sure you navigate to the `\marklogic_powerbi_tutorial\config` directory.
	
	The MCLP loading instructions are in the mlcp workspace following tabs:
	
	* `mlcp script load orders`
	* `mlcp script load people data`
	* `mlcp script load returns`
	
	> Note: loading the orders data can take up to 3 minutes.

5. Explore the Documents database.  
	Check that documents were added to the Documents database by clicking the **explore** button.

6. Check the views.  
Make sure the `Query Type` is set to **SQL**. Run the scripts from the following tabs.

	* `select count(*)`
	* `select sys_tables`

7. Setup an ODBC application server
Run the script from the `create odbc app server` workspace tab.

8. Install the MarkLogic ODBC Driver (64 bit or 32 bit)
Download the drivers from <https://developer.marklogic.com/products/odbc>. Ensure you have the correct 64 bit or 32 bit driver depending if PowerBI is 64 bit or 32 bit.

9. Create a DSN with your ODBC app server and Schema name

10. Install the Power BI Desktop version matching your ODBC driver word length version (64 or 32 bit)

11. Import the **Global Super Store** data to Power BI Desktop.

	* Select **Get Data** > **More** > **Other** > **ODBC** > **Connect** > **Select Data Source Name (DSN)**
	* Your Schema and view(s) appear in the navigator. 
	* Select the ones to load.
	* Create some PowerBI Reports over your data.
