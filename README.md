# BloodBankRUs
A java program that uses SQL queries to update and moniter a donor management system for a blood bank 

public class Donor {
    // declaring connection and variables of data sources
    

    // initialise method initialises the database with the DonorDat of our bloodbank it also sets the URL to the database file
    // it then gets the connection to the database and creates a statement object, which is used to execute the SQL query to create the table DonorData if the table does not already exist
    public static void dbInit() {
        ds = new SQLiteDataSource();

      
            String query = "CREATE TABLE IF NOT EXISTS DonorData ("
                  

    //function to insert donor data into database it takes in various arguments and creates an SQL query to insert data in database
// the arguments: donor id donor name blood type donor join date donor gender donor contact donor email donor address
   
    protected static void insertDonorData(String id, String name, String type, String joinDate, String gender, String contact, String email, String address) throws SQLException {
        String query = "INSERT INTO DonorData("
              
      

    // this function is for updating donor data
    //It creates an SQL query to update the data for the particular Donor based on the ID, and executes it using the statement object
   
    protected static void updateDonorData(String id, String name, String type, String joinDate, String gender, String contact, String email, String address) throws SQLException {

        String query = "UPDATE DonorData"
                + "SET"

                + "WHERE"
                + "Donor_id='" + id + "'";

  

    // function to delete entry from database
    // It creates an SQL query to delete the data for the particular Donor based on the ID, and executes it using the statement object
  
    protected static void deleteDonorData(String id) throws SQLException {
        String query = "DELETE FROM DonorData WHERE Donor_id = '" + id + "';";
       
    // function used to search for a particular donor using the id,email or name as an argument and creates an SQL query to retrieve the data for the particular employee
    //It then executes the query using the statement object and returns the result set, which contains the data for the searched employee
   
    public static void searchDonorData(DefaultTableModel model, String searchTerm, String column) throws SQLException {
        model.setRowCount(0);
        String query = "SELECT * FROM DonorData WHERE " + column + " LIKE '%" + searchTerm + "%';";
       
        ResultSet ResSet = statement.executeQuery(query);
        while (ResSet.next()) {
           
            model.addRow(new Object[]{
                    id, name, type, joinDate, gender, contact, email, address
            });  // a dds each row of data as a new row to the DefaultTableModel by calling the addRow method and passing an array of objects representing the columns of a row

        }
        con.close();
        ResSet.close(); // closes the database connection and the Result object

    }

    // function to clear the current data from a DefaultTableModel by calling the setRowCount method with an argument of 0
    // Define an SQL query to select all the data from the data table and connects to the database using a DataSource object ds by calling its getConnection method and stores the connection object
    // Creates a Statement object using the connection object and executes the query as well as iterates through the ResultSet returned from the query execution and retrieves the values of the columns for each row

    public static void loadData(DefaultTableModel model) throws SQLException {
        model.setRowCount(0);
        String query = "SELECT * FROM DonorData;";
      
        while (ResSet.next()) {
           
            model.addRow(new Object[]{
                    id, name, type, joinDate, gender, contact, email, address
            });  //Then, Adds each row of data as a new row to the DefaultTableModel by calling the addRow method and passing an array of objects representing the columns of a row
        }
        con.close();
        ResSet.close(); // finally, closes the database connection and the ResultSet object
    }
}



