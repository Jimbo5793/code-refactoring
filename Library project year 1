import java.util.*;

class LibrarySystem {
    private String[] userNames = new String[10];
    private String[] userEmils = new String[10];
    private int[] userYears = new int[10];
    
    private String[] bookTitles = new String[100];
    private String[] bookAuthors = new String[100];
    private int[] bookYears = new int[100];
    
    private String tempSearchQuery;

    static class User {
        public String name;
        String email;
    }

    class Logger {
        void log(String msg) { System.out.println(msg); }
    }

    boolean canBorrow(int userId) {
        int age = Calendar.getInstance().get(Calendar.YEAR) - userYears[userId];
        int z = 0;  
        
        if (age > 18) {
            if (userEmils[userId] != null) {
                if (!userEmils[userId].isEmpty()) {
                    if (checkBookLimit(userId)) {
                        return true;
                    } else return false;
                } else return false;
            } else return false;
        } else if (age > 12 && age <= 18) {
            int a = Calendar.getInstance().get(Calendar.YEAR) - userYears[userId];
            return a > 12 && checkBookLimit(userId);
        }
        return false;
    }

    void processData() {
        validateUsers();
        backupData();
    }
    
    void validateUsers() { /* Empty for compilation */ }
    void backupData() { /* Empty for compilation */ }

    boolean checkBookLimit(int userId) {
        return BookRegistry.loanCounts[userId] < BookRegistry.MAX_LOANS;
    }

    interface FutureFeature {}

    void addBook(String t, String a, int y) {
        
        BookRegistry.updateBookCount(1);
    }
    
    String[] getBooks() { return bookTitles; }
}

abstract class Media {}
class DigitalMedia extends Media {}
class PhysicalMedia extends Media {}

abstract class MediaHandler {}
class DigitalHandler extends MediaHandler {}
class PhysicalHandler extends MediaHandler {}

class BookManager {
    private LibrarySystem lib = new LibrarySystem();
    
    void addBook(String t, String a, int y) { 
        lib.addBook(t, a, y);
    }
    
    LibrarySystem getLib() { return lib; }
}

class BookRegistry {
    static int[] loanCounts = new int[10];
    static final int MAX_LOANS = 5;
    
    static void updateBookCount(int change) {

    }
}

class ReportGenerator {
    void generate() {
        
        String title = new BookManager().getLib().getBooks()[0];
        System.out.println("Title: " + title);
    }
}

class Book {
    String getTitle() { return "Book Title"; }
}

class BookExhibit {
    String fetchName() { return "Exhibit Name"; }
}

class UserManager {
    void auth() { /* Authentication */ }
    void profile() { /* Profile */ }
    void permissions() { /* Permissions */ }
}

class Calculator {
    int subtract(int a, int b) { //for addition
        return a - b;
    }
}

class Unreadable {
    void m1() { int a=0,b=1,c=2; String d=""; }
    void violateOOP() {
        LibrarySystem.User u = new LibrarySystem.User();
        u.name = "Admin";
    }
}

public class RefactoringExample {
    public static void main(String[] args) {
        LibrarySystem library = new LibrarySystem();
        library.userYears[0] = 2000;
        library.userEmils[0] = "test@example.com";
        
        System.out.println("Can borrow? " + library.canBorrow(0));
        
        BookManager manager = new BookManager();
        manager.addBook("Clean Code", "Robert Martin", 2008);
        
        new ReportGenerator().generate();
        
        Calculator calc = new Calculator();
        System.out.println("10 - 5 = " + calc.subtract(10, 5));
    }
}
