# Library Management System (OOP Project)

class Book:
    def __init__(self, title, author, copies):
        self.title = title
        self.author = author
        self.copies = copies

    def is_available(self):
        return self.copies > 0

    def borrow(self):
        if self.is_available():
            self.copies -= 1
            return True
        return False

    def return_book(self):
        self.copies += 1


class Member:
    def __init__(self, name):
        self.name = name
        self.borrowed_books = []

    def borrow_book(self, book):
        if book.borrow():
            self.borrowed_books.append(book)
            print(f"{self.name} borrowed '{book.title}'")
        else:
            print(f"'{book.title}' is not available.")

    def return_book(self, book):
        if book in self.borrowed_books:
            book.return_book()
            self.borrowed_books.remove(book)
            print(f"{self.name} returned '{book.title}'")
        else:
            print(f"{self.name} does not have '{book.title}'")


class Library:
    def __init__(self):
        self.books = []

    def add_book(self, book):
        self.books.append(book)

    def show_available_books(self):
        print("\nAvailable Books:")
        for book in self.books:
            print(f"{book.title} by {book.author} - Copies: {book.copies}")


# Example usage
if __name__ == "__main__":
    # Create library and add books
    lib = Library()
    b1 = Book("Python Basics", "Ali Khan", 3)
    b2 = Book("Data Structures", "Sania Irshad", 2)
    b3 = Book("OOP Concepts", "Fatima Noor", 1)

    lib.add_book(b1)
    lib.add_book(b2)
    lib.add_book(b3)

    # Create a member
    m1 = Member("Ahsan")

    # Member borrows books
    lib.show_available_books()
    m1.borrow_book(b1)
    m1.borrow_book(b3)
    lib.show_available_books()

    # Member returns a book
    m1.return_book(b3)
    lib.show_available_books()
