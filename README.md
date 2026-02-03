# My-First-Assignment-Project

This repository contains my SQL script for Assignment 1. It creates a database called `MyTestDb` with two tables (`Authors` and `Books`), includes primary keys and a foreign key relationship, and contains sample inserts and SELECT queries.

-- Q1. Create a database called MyTestDb.
-- Step 1: Creating Database MyTestDb
CREATE DATABASE IF NOT EXISTS MyTestDb;
-- Step 2: Select Database MyTestDb
USE MyTestDb;

-- Q2. create the table of Authors.
-- Step 3: Creating Authors Table
CREATE TABLE IF NOT EXISTS Authors (
AID INT PRIMARY KEY,
AFName VARCHAR(32),
ALName VARCHAR(32),
AStAddress VARCHAR(32),
ACity VARCHAR(32),
AState VARCHAR(32),
AZipcode VARCHAR(32),
ADOB DATE);

-- Q3. create the table of Books
-- Step 4: Creating Books Table
CREATE TABLE IF NOT EXISTS Books (
BID INT PRIMARY KEY,
BName VARCHAR(32),
BISBN VARCHAR(13),
BPDate DATE,
AID INT,
FOREIGN KEY(AID) REFERENCES Authors(AID));

-- Q4. add at least two authors to the table of Authors
-- Step 5: Inserting values in Authors Table
INSERT IGNORE INTO Authors(AID, AFName, ALName, AStAddress, ACity, AState, AZipcode, ADOB) VALUES
(1, 'George', 'Orewell', '4123 Elm St', 'Austin', 'TX', 77024, '1904-10-14'),
(2, 'Jane', 'Doe', '45 Oak Ave', 'Dallas', 'TX', 77054, '1904-09-25'),
(3, 'Donald', 'Knuth', '1 CS Way', 'Stanford', 'CA', 94305, '1938-01-10'),
(4, 'Andrew', 'Tanenbaum', '2 Net Way', 'Amsterdam', 'NH', 1012, '1944-03-16');

-- Q5. add at least four books to the table of Books
-- Step 6: Inserting values in Books Table
INSERT IGNORE INTO Books(BID, BName, BISBN, BPDate, AID) VALUES
(101, '1984', '9780451524935', '1949-06-08', 1),
(102, 'Animal Farm', '9780451526342', '1949-08-17', 1),
(103, 'Pride and Prejudice', '9780141439518', '1813-01-28', 2),
(104, 'Emma', '9780141439587', '1815-12-23', 2),
(105, 'TAOCP Vol 1', '9780201896831', '1997-01-01', 3),
(106, 'TAOCP Vol 2', '9780201896848', '1997-01-01', 3),
(107, 'TAOCP Vol 3', '9780201896855', '1997-01-01', 3),
(108, 'Computer Networks', '9780132126953', '2010-10-01', 4),
(109, 'Modern Operating Sys', '9780133591620', '2014-03-01', 4),
(110, 'Computer Netw 5e', '9780132126953', '2010-10-01', 4);

SELECT * FROM Authors;
SELECT * FROM Books;
