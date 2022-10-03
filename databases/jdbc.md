
## Læringsmål
* Forbind en spring boot webapplikation med en mysql database.


## Materiale


## Kode fra sql undervisningen 

```
public class ConnectionExample {
    public static void main(String[] args) {
        try{
            Connection conn = DriverManager.getConnection("jdbc:mysql://[HOSTNAME]/[YOUR DATABASE NAME]","[YOUR USERNAME]","[YOUR PASSWORD]");
            PreparedStatement psts = conn.prepareStatement("SELECT * from employees");
            ResultSet resultSet = psts.executeQuery();
            while(resultSet.next()){
                System.out.println(resultSet.getString(2));
            }

        }catch(SQLException e){
            System.out.println("Cannot connect to database");
            e.printStackTrace();
        }
    }
}

```

 

### Generer et dump af din database

```
	$ mysqldump --opt -u [uname] -p [pass] [dbname] > [backupfile.sql]
```


## Øvelser

