
CHAR(N) = ตัวอักษร ยางคงที่ max 255 char
VARCHAR(N) = จัวอักษร ไม่คงที่ max 4000 char

DEC(M, N) M = จำนวนเลขทั้งหมด (รวม ทศนิยม),  N = จำนวนตัวเลขหลังจุดทศนิยม
FLOAT

INT = -2,147,483,648 ถึง 2,147,483,648
SMALLINT = -32,768 ถึง 32,768
NUMBER(N) = จำนวนจริง

BIT = 1 - 64

INT UNSIGNED = INT ไม่มีค่าติดลบ = 0 ถึง 4,294.967,295

BOOLEAN = 1, 0

(DATE/TIME)

yyyy-mm-dd   (2024-01-31)
dd.mm.yyyy    (31. 01. 2024)
dd/mm/yyyy   (31/01/2024)


# TABLE

CREATE TABLE <Table Name>
( 
<Column Name> <Data Type> <NOT NULL> <UNIQUE>,
<Column Name> <Data Type> <NOT NULL> <UNIQUE>,
... )

NOT NULL = ห้ามเป็นค่าว่าง
UNIQUE = ห้ามมีค่าซ้ำกัน


คอลัมน์เดียวเป็น Primary Key

CREATE TABLE STUDENT
( STUDENT_ID INT NOT NULL UNIQUE *PRIMARY KEY* );

คอลัมน์มากกว่า 1 Column เป็น Primary Key

CREATE TABLE STUDENT
( 
   FIRSTNAME CHAR(10) NOT NULL,
   LASTNAME CHAR(10) NOT NULL UNIQUE,
   PRIMARY KEY (FIRSTNAME, LASTNAME)
 );

FOREIGN KEY

CREATE TABLE STUDENT
( 
  STUDENT_ID INT NOT NULL UNIQUE PRIMARY KEY,
  FOREIGN KEY (CLASSROOM_NO) REFERENCES CLASS(CLASSROOM_NO)
);


DROP TABLE

DROP TABLE <Table Name> [ CASCADE CINSTRAINTS ];

CASCADE CONSTRAINTS = ระบบจัดการฐานข้อมูลที่จะทำการลบ ข้อจำกัดต่างๆ (constraint) ที่มีการอ้างถึงตารางทิ้งไปให้ด้วยทั้งหมด


ALTER TABLE

ใช้ในการเพิ่ม column, เปลี่ยนชื่อ column, แก้ไข column

ALTER TABLE <Table Name>
DATABASE UPDATE ( <COLUMN NAME> data type [SIZE] );

Database update = คำสั่งการเปลี่ยแปลง
data type [SIZE] = ชนิดข้อมูล, ขนาดของข้อมูล

ALTER TABLE SALESPEOPLE ADD SALESTAB_FAX CHAR(15);
ALTER TABLE SALESPEOPLE MODIFY SALESTAB_FAX CHAR(30);
ALTER TABLE SALESPEOPLE RENAME ADDRESS TO COUNTRY;


CREATE INDEX
CREATE [UNIQUE] INDEX <index name> ON <table name>
(
	<column name> [, <column name>]..
);

DROP INDEX <index name>;


INSERT

INSERT INTO <table name> [(column 1, column2, ...)] VALUES (<value1, value2, ...>);


INSERT INTO SALESTAB VALUES (1001, "Chaiwat", 'Bangkok" 0.12)

INSERT INTO CUSTOMERSTAB(ADDRESS, CUSNAME, CUSNO)
VALUES ('Bangkok', 'Arlee', 2001);


นำค่าจากตารางหนึ่งไปใส่อีกตารางหนึ่ง

INSER INTO <table name>[(column 1, column 2, ...)]
SELECT statement;

INSERT INTO BANGKOKSTAFF
SELECT * 
FROM SALESTAB
WHERE ADDRESS = 'Bangkok';


UPDATE

UPDATE <table name>
SET <column name> = <new value>
[WHERE <condition>];

UPDATE CUSTOMERTAB
SET RATING = 200;

UPDATE CUSTOMERTAB
SET RATING = 200
WHERE SALENO = 1001;


DELETE


DELETE FROM <table name>
[WHERE <condition>];

DELETE FROM SALESTAB
WHERE SALENO = 1003;

SELECT

SELECT *
FROM <table name>;

SELECT *
FROM checks;

SELECT <column 1, column 2, ...>
FROM <table name>;


SELECT DISTINCT

Distinction = ไม่แสดงข้อมูลซ้ำ มาแค่ครั้งเดียว




SELECT FROM WHERE <condition>

SELECT FROM WHERE
ORDER BY <column 1, column 2, ...> [ASC] [DESC];

ASC = น้อยไปมาก
DESC = มากไปน้อย

SELECT PAYEE
FROM CHECKS
WHERE PAYEE LIKE ('CA%');

SELECT PAYEE
FROM CHECKS
WHERE PAYEE STARTING WITH ('Ca');

SELECT PAYEE
FROM CHECKS
WHERE PAYEE  STARTING WITH ('Ca')
OR REMARKS LIKE 'G%';

% = ขึ้นต้นด้วย หรือ ลงท้ายด้วย แล้วแต่ว่าวางไว้ไหน
_ = แทนตัวอักษรไม่ทราบค่า 1 ตัว
STARTING WITH = ขึ้นต้นด้วย



SELECT AND, OR

SELECT FROM WHERE 
<condition>
AND
<condition>

SELECT FROM WHERE 
<condition>
OR
<condition>


AGGREGATE FUNCTIONS

COLUNT (*) นับแถวทั้งหมด
COUNT (DISTINCT COLUMN) นับไม่รวมค่าซ้ำและ NULL

SUM, AVG, MAX, MIN

SELECT COUNT(*)
FROM TEAMGAME;

SELECT COUNT(*) AS HIT_BELOW_60
FROM TEAMGAME
WHERE HITS < 60;