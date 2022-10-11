# table_sql
sql table

import sqlite3 as sq
#Подключение к файлу БД сапер
with sq.connect("saper.db") as con:
    cur = con.cursor()
#"""кон ссылка и витз (контекст менеджера)"""
#"""клоз не нужен т к виз закроет БД без потери данных"""
#"""если не существует таблица юзерс, то она создается ИФ НОТ"""

    cur.execute("DROP TABLE IF EXISTS users")
    cur.execute(""" CREATE TABLE IF NOT EXISTS users (
        user_id INTEGER PRIMARY KEY AUTOINCREMENT,
        name TEXT NOT NULL,
        sex INTEGER NOT NULL DEFAULT 1,
        old INTEGER,
        score INTEGER
        )""")
