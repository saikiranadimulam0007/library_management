from db.connection import get_connection

class BookDAO:

    @staticmethod
    def add_book(book):
        conn = get_connection()
        cursor = conn.cursor()
        cursor.execute("""
            INSERT INTO books (title, author, isbn, category, total_copies, available_copies)
            VALUES (?, ?, ?, ?, ?, ?)
        """, (book.title, book.author, book.isbn, book.category, book.total, book.available))
        conn.commit()
        conn.close()

    @staticmethod
    def get_all_books():
        conn = get_connection()
        cursor = conn.cursor()
        cursor.execute("SELECT * FROM books")
        data = cursor.fetchall()
        conn.close()
        return data

    @staticmethod
    def search_book(keyword):
        conn = get_connection()
        cursor = conn.cursor()
        cursor.execute("""
            SELECT * FROM books
            WHERE title LIKE ? OR author LIKE ? OR isbn LIKE ?
        """, (f"%{keyword}%", f"%{keyword}%", f"%{keyword}%"))
        data = cursor.fetchall()
        conn.close()
        return data

    @staticmethod
    def delete_book(book_id):
        conn = get_connection()
        cursor = conn.cursor()
        cursor.execute("DELETE FROM books WHERE book_id = ?", (book_id,))
        conn.commit()
        conn.close()
