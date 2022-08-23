# Ex: Client vs Library Code

I denne tutorial skal du arbejde med nogle eksempler på Client code og Library code, og du vil få en bedre forståelse for dette og for abstraction i det hele taget.

#### Bibliotek

I går lavede du en øvelse med en Bog og et bibliotek.

```java
public class Book {
    private String title;
    private String author;
    private String isbn;
    private int year;

    public Book(String title, String author, String isbn, int year) {
        this.title = title;
        this.author = author;
        this.isbn = isbn;
        this.year = year;
    }
    
    // Getter and Setters for all Fields (attributes)
}
```

```java
public class Library {

    ArrayList<Book> books = new ArrayList<>();

    public Library() {
        books.add(new Book("War Thunder", "John Doe", "123456789", 2019));
        books.add(new Book("Hacknet", "John Doe", "234567891", 2013));
        books.add(new Book("Hacknet", "John Doe", "345678912", 2022));
        books.add(new Book("Hacknet", "John Doe", "456789123", 2021));
    }

    public boolean doesBookExist(Book book){
        for (Book b : books) {
            if (b.getIsbn().equals(book.getIsbn())){
                return true;
            }
        }
        return false;
    }
}a
```

Du skal arbejde videre med den kode som grundlag.&#x20;

