```mermaid
classDiagram
    class User {
        -id: int
        -name: String
        -email: String
        -password: String
        +login() boolean
        +logout() void
    }
    
    class Member {
        -memberCode: String
        -joinDate: Date
        -activeLoans: int
        +borrowBook() boolean
        +returnBook() boolean
        +renewLoan() boolean
    }
    
    class Librarian {
        -employeeId: String
        +addBook() void
        +removeBook() void
        +confirmReturn() void
    }
    
    class Book {
        -isbn: String
        -title: String
        -author: String
        -available: boolean
        +getDetails() String
    }
    
    class Loan {
        -loanId: int
        -borrowDate: Date
        -dueDate: Date
        -status: String
        +calculateFine() float
    }
    
    User <|-- Member
    User <|-- Librarian
    Member "1" -- "*" Loan
    Book "1" -- "*" Loan