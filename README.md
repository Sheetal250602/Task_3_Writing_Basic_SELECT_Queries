# Task_3_Writing_Basic_SELECT_Queries
# Using 'Library' database and two tables 'Author' and 'Books' by using MySQL Workbench.

CREATE DATABASE LibraryDB;
USE LibraryDB;

CREATE TABLE Author(
Author_id INT PRIMARY KEY,
first_name VARCHAR(50),
last_name VARCHAR(50)
);

INSERT INTO Author Values
(101, 'William', 'Shakespeare'),
(102, 'Rabindranath', 'Tagore'),
(103, 'Hariwanshrai', 'Bachchan');

CREATE TABLE Books(
Book_id INT PRIMARY KEY,
Title VARCHAR(100),
published_year DATE,
Author_id INT NOT NULL,
FOREIGN KEY(Author_id) REFERENCES Author(Author_id)
);

INSERT INTO Books Values
(1, 'Romeo And Juliet', '1597-01-01', 101),
(2, 'Gitanjali', '1910-01-01', 102),
(3, 'Madhushala', '1935-01-01', 103);

# Extracting data from both BOOKS and AUTHOR Tables:
SELECT * FROM Books;

# <img width="418" height="153" alt="image" src="https://github.com/user-attachments/assets/0cab4ab1-730f-4a73-8d48-dc16af1e7d97" />

SELECT * FROM Author;

# <img width="310" height="154" alt="image" src="https://github.com/user-attachments/assets/6adaf701-2009-467f-9038-c8964b17c1fd" />

# Extracting specific columns by Using "SELECT" Query:
SELECT Author_id, first_name FROM Author;

# <img width="234" height="147" alt="image" src="https://github.com/user-attachments/assets/38b07b21-05eb-480f-961e-9e130b67c340" />


# Using "WHERE" clause:
SELECT * FROM Books
WHERE Title = 'Gitanjali';

# <img width="360" height="99" alt="image" src="https://github.com/user-attachments/assets/8df7de20-8313-4102-8442-a91f20d228c6" />


# Using "AND" Operator:
SELECT * FROM Books 
WHERE Title = 'Gitanjali' AND Author_id = 102;

# <img width="360" height="99" alt="image" src="https://github.com/user-attachments/assets/8df7de20-8313-4102-8442-a91f20d228c6" />

# Using "OR" Operator:
SELECT * FROM Books
WHERE Book_id = 3 OR Title = 'Gitanjali'; 

# <img width="375" height="111" alt="image" src="https://github.com/user-attachments/assets/b773e30c-5d01-4d98-a405-f7506722ae86" />


# Using "LIKE" Operator:
SELECT * FROM Author
WHERE first_name LIKE 'W%';

# <img width="298" height="108" alt="image" src="https://github.com/user-attachments/assets/14150ad2-1bd8-44df-a0d4-1661b4d73897" />


# Using "BETWEEN" Operator:
SELECT * FROM Books
WHERE published_year BETWEEN '1500-01-01' AND '1920-01-01';

# <img width="412" height="107" alt="image" src="https://github.com/user-attachments/assets/9476600b-742a-47c8-bf8f-759bcc30821d" />


# Using "ORDER BY" Clause:
SELECT * FROM Author
ORDER BY first_name;

# <img width="306" height="149" alt="image" src="https://github.com/user-attachments/assets/7ad57f20-6a90-4f60-b749-89a8a15fd4f2" />


# Using "LIMIT" Clause:
SELECT * FROM Books
WHERE Title LIKE 'G%'
LIMIT 1;

# <img width="363" height="83" alt="image" src="https://github.com/user-attachments/assets/40d3051f-cc6b-4cb0-a25c-df0b5d4ca03a" />
