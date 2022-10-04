
## Læringsmål
* Forbind en spring boot webapplikation med en mysql database.
* Læse fra en tabel i databasen og ligge resultatet i en List<> og vise resultatet i browseren vha. @RestController.
* Lære at brug et singleton design pattern. 

## Materiale


## Kode fra sql undervisningen 


## Forbind Spring Boot og database

```
public class DatabaseConnectionManager {
    private static String hostname;
    private static String username;
    private static String password;
    private static Connection conn;

    public static Connection getConnection(){
        if(conn != null){
            return conn;
        }

        hostname = "jdbc:mysql://clbodat22v1.mysql.database.azure.com/pokedex";
        username = "clbo";
        password = "Kea_pass";
        try {
            conn = DriverManager.getConnection(hostname, username, password);
        } catch (SQLException e) {
            e.printStackTrace();
        }
        return conn;
    }
}
```

 

### Generer et dump af din database

```
	$ mysqldump --opt -u [uname] -p [pass] [dbname] > [backupfile.sql]
```


## Øvelser

### Movie Workshop, (nu med Database)


#### MySQL Driver dependency
Cope/paste dette ind i din pom.xml fil.

```
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <scope>runtime</scope>
        </dependency>
```

Du kunne også have afkrydset **MySql Driver** under dependencies da du oprettede projektet. 

![](assets/MySqlDriver.png)



