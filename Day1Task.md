		

	#	ASSIGNMENT-1
	-------------------------
	-------------------------

/*--------(A)---------*/

create table SALESPEOPLE
(
 Snum int(4),
 Sname varchar(10),
 City varchar(10),
 Comm float(3,2) 
);

insert into SALESPEOPLE values 
(1001,'Peel','London',.12),
(1002,'Serres','San Jose',.13),
(1004,'Motika','London',.11),
(1007,'Refkin','Barcelona',.15),
(1003,'Axelrod','New York',.10);

show tables;

select * from SALESPEOPLE;

/*........(B)........*/

create table CUSTOMER
(
    Cnum int(4),
    Cname varchar(10),
    City varchar(10),
    Rating int(4),
    Snum int(4) 
);

insert into CUSTOMER values 
(2001,'Hoffman','London',100,1001),
(2002,'Givovanni','Rome',200,1003),
(2003,'Liu','San Jose',200,1002),
(2004,'Grass','Berlin',300,1002),
(2006,'Celemens','London',100,1001),
(2008,'Cisneros','San Jose',300,1007),
(2007,'Pereira','Rome',100,1004);

select * from CUSTOMER;

/*-------(C)--------*/

create table ORDERS
( 
    Onum int(4),
    Amt float(7,2),
    Odate date,
    Cnum int(4),
    Snum int(4) 
);

insert into ORDERS values 
(3001,18.69,'1990-10-03',2008,1007),
(3003,767.19,'1990-10-03',2001,1001),
(3002,1900.10,'1990-10-03',2007,1004),
(3005,5160.45,'1990-10-03',2003,1002),
(3006,1098.16,'1990-10-03',2008,1007),
(3009,1713.23,'1990-10-04',2002,1003),
(3007,75.75,'1990-10-04',2004,1002),
(3008,4723.00,'1990-10-05',2006,1001),
(3010,1309.95,'1990-10-06',2004,1002),
(3011,9891.88,'1990-10-06',2006,1001);

select * from ORDERS;

		SQL EXERCISE 1
	---------------------------
	---------------------------

Q 1. Create the table SEMP with the following structure:-

EMPNO CHAR(4)
EMPNAME CHAR(20)
BASIC FLOAT(9,2)
DEPTNO CHAR(2)
DEPTHEAD CHAR(4) 

ANS :-

create Table SEMP
(
	EMPNO CHAR(4),
        EMPNAME CHAR(20),
	BASIC FLOAT(9,2),
	DEPTNO CHAR(2),
	DEPTHEAD CHAR(4)
);

2. Create the table SDEPT with the following structure:-

DEPTNO CHAR(2)
DEPTNAME CHAR(15) 

ANS :-

create table SDEPT
(
	DEPTNO CHAR(2),
	DEPTNAME CHAR(15) 
);

3. Insert into the SDEPT table the following values:-

10, Development
20, Training 

ANS :-

insert into SDEPT values('10','Development'),('20','Training');

select * from SDEPT;

4. Insert into the SEMP table the following values:-

0001, SUNIL, 6000, 10
0002, HIREN, 8000, 20
0003, ALI, 4000, 10, 0001
0004, GEORGE, 6000, 0002 

ANS :-

insert into SEMP values
('0001', 'SUNIL', 6000, '10', null ),
('0002', 'HIREN', 8000, '20', null),
('0003', 'ALI', 4000, '10', '0001' ),
('0004', 'GEORGE', '6000',null, '0002' );

select * from SEMP;


Create S, P, J, SPJ tables as specified below and insert a few rows in each table:-

SUPPLIER
(S#, Sname, Status, City)
- S
PARTS
(P#, Pname, Color, Weight, City)
- P
PROJECTS
(J#, Jname, City)
- J
SUPPLIER-PARTS-PROJECT
(S#, P#, J#, Qty)

- SPJ
Sample data for S# column:- ‘S1’, ‘S2’, ‘S3’, etc.
Sample data for P# column:- ‘P1’, ‘P2’, ‘P3’, etc.
Sample data for J# column:- ‘J1’, ‘J2’, ‘J3’, etc.
Sample data for Status column:- 10, 20, 30, etc.

Ans:-
create table SUPPLIER 
(
    Sid  CHAR(4),
    Sname VARCHAR(20),
    Sstatus INT(20),
    City CHAR(20)
);

create table PARTS
(
    Pno VARCHAR(10),
    Pname VARCHAR(20),
    Color CHAR(10),
    Weight VARCHAR(10),
    City CHAR(20)
);


create table PROJECTS
(
    Jno VARCHAR(10),
    Jname VARCHAR(20),
    City VARCHAR(20)
);

create table SUPPLIER_PARTS_PROJECT 
(
    Sid CHAR(4),
    Pno VARCHAR(10),
    Jno VARCHAR(10)
);

Write the SELECT queries to do the following:-

5. Display all the data from the S table.
	select * from SUPPLIER;

6. Display only the S# and SNAME fields from the S table.
	select Sid, Sname from SUPPLIER;

7. Display the PNAME and COLOR from the P table for the CITY=”London”.
	select Pname, Color from PARTS where City='London';

8. Display all the Suppliers from London.
	select * from SUPPLIER where city='London';

9. Display all the Suppliers from Paris or Athens.
	select * from SUPPLIER where city='Paris'or'Athens';

10. Display all the Projects in Athens.
	select * from PROJECTS where city='Athens';

11. Display all the Partnames with the weight between 12 and 14 (inclusive of both).
	select Pname,Weight from PARTS where Weight>=12 or Weight<=14;

12. Display all the Suppliers with a Status greater than or equal to 20.
	select Sname, Sstatus from SUPPLIER where Sstatus>=20;

13. Display all the Suppliers except the Suppliers from London.
	select * from SUPPLIER where City!='London';

14. Display only the Cities from where the Suppliers come from.
	select City from SUPPLIER;

15. Assuming that the Part Weight is in GRAMS, display the same in
MILLIGRAMS and KILOGRAMS. 
	select Weight*1000 , Weight/1000 from PARTS;
