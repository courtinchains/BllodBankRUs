# BloodBankRUs
A java program that uses SQL queries to update and moniter a donor management system for a blood bank 
It declaring connection and variables of data sources then initialise method initialises the database with the DonorDat of our bloodbank it also sets the URL to the database file
it then gets the connection to the database and creates a statement object, which is used to execute the SQL query to create the table DonorData if the table does not already exist.
Next a function is used to insert donor data into database it takes in various arguments and creates an SQL query to insert data in database
the arguments: donor id donor name blood type donor join date donor gender donor contact donor email donor address. 
A function for updating the donor data is then created as well as a function to delete an entry from the database by creating an SQL query to delete the data for a particular donor based on the id of the donor. A function used for searching a patricular donor based on any arguement is created as well. 
Lastly, a fucntion is created to define an SQL query to select all data from the table data and connects to the database using a datasource object and stores the connection object it then interates through the resultset returned from the query execution and retrives the values of the columns for each row.  
It then adds each row of data as a new row to the defaulttablemodel and lastly closes the database connection and the resultset object.
