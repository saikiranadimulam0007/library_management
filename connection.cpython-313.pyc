from service.book_service import BookService

class BookController:

    @staticmethod
    def add_book():
        title = input("Title: ")
        author = input("Author: ")
        isbn = input("ISBN: ")
        category = input("Category: ")
        total = int(input("Total Copies: "))

        BookService.add_new_book(title, author, isbn, category, total)
        print("✅ Book added successfully")

    @staticmethod
    def view_books():
        books = BookService.view_books()
        print("\n--- Book List ---")
        for b in books:
            print(b)

    @staticmethod
    def search_book():
        key = input("Enter title / author / ISBN: ")
        result = BookService.search_books(key)
        for r in result:
            print(r)

    @staticmethod
    def delete_book():
        book_id = int(input("Enter Book ID to delete: "))
        BookService.remove_book(book_id)
        print("❌ Book deleted")
