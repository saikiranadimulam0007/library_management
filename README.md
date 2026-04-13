import sqlite3

DB_NAME = "library.db"

def get_connection():
    try:
        conn = sqlite3.connect(DB_NAME)
        conn.execute("PRAGMA foreign_keys = ON")
        return conn
    except Exception as e:
        print("Database connection error:", e)
        return None
