# SQL
DBMS BASICS AT ONE PLACE 
 RDBMS IS A software which can be access by SQL 

 //diff b/w SQL & MYSQL 
 sql - it is a programming language . 
 mysql - it is a open source RFBMS software where crud operation can be performed 

 //dtabase created
creat DATABASE temp ;
SHOW DATABASE;
use temp ;

//creat table 
CREAT TABLE STUDENT (
ID INT PRIMARAY KEY,
nmae VARCHAR(255)
):

INSERT INTO student(1 , 'nidhi');
SELECT * FROM student ;
DROP DATABASE IF EXISTS temp ;

//SQL DATA TYPE - 
char , varchar ,tinytext - string(0 , 255) ,blog(store video) 
ENUM (one of the present value) &&&&&&&&&&&&&& set (one or many of present value)

// type of command 
1. DDL (data definition language)
    CREAT - creat a atabke 
     ALTER - alter the col , table
   DROP - delete the table
   TRUCATE - delete all the tuple
   RENAME - rename coloum , table name

   2. DRL - (DATA  retevral language ) select
  
   3. dml - (data modification language )
    INSERT - insert te data in reletion
    UPDATE - update data in the relation 
    DELETE - delete the row(s)

   4. DCL - (DATA CONTOL LANGUAGE )
      GRANT - access the db 
      REVOKE - denay access privelage 
   5.TCL - (transection control language )
      start tranjection - begin
      commit - apply all changes and end the trenjections
      rollback - discard the changes and end the trenejction
      savepoint - check out from where to rollback

CREAT TABLE WORKER(
WORKER_ID INT NOT NULL PRIMERY KEY AUTO_INCREMENT k
FIRST_NAME char(25),
LAST_NAME char(25),
DEPARTURE_TIME DATETIME ,
salary INT ,
DEPARTMENT CHAR(25);
);

INSERT INTO worker 
( WORKER_ID , FIRST NMAE , LAST ANME , DEPARTURE TIME , SALARY ) VALUES ;
( 20 ,'nidhi' , 'rai' ,'14-08-2023 16.30.00' , 20,000 ,'HR'),
(21 , 'riya' , 'rai' , '16-08-2023 16.40.43' , 22,000 , 'HR');
SELECT * from WORKER ;
//SYNTEX TO SELECT SET OF COLOUM FROM  THE TABLE ONLY = select <set of coloum name> from <table name>
SELECT FIRST_NAME , LAST_ANME  from WORKER 

CREAT TABLE other(
FIRAT_NAME char(25) ,
last_name char(25) ,
WORKER_REF_ID INT FOREGIN KEY 


DRL/DQL 
1.select<set cf coloum name > from <table name>
2.order of eecution from right to left
3.***** cwe can also use SELECT KEYWORD withut using from clause by using DUAL TABLE OR DUMMY TABLE 
eg - SELECT 44+11 ;  SLECTE NOW() ;

4. WHERE - SLECTE * from WORKER WHERE salaary > 10,000 ;
5. BETWEEN - SELECT * FROM WORKER WHERE SALARY BETWEEN 20,000 AND 30,000 ;
6. SELECT * FROM WORKER WHERE SALARY = 20,000 0R SALARY = 25,000 ;
7. SELECT * FROM WORKER WHERE SALARY IN (20,000 , 24,000 , 30,000) ;
8. AWLWCT * FROM WHERE SALARY NOT IN = 20,000 ;
9. IS NULL
10. SLECT * FRON WHER FIRST_NAME LIKE '%I%' ;
11. SORTING USING ORDER BY - SELECT *FROM WHERE ORDER BY SALARY ; (BY DEFAULT ACCEDNDING FOR DECENDING DESC )
12. DISTINT - SELECT DISTINT SALARY FROM WORKER
13. GROUP BY 
//IT USES FOR THE AGGRIGAIIN PUPOSES LIKE SUM , MAX , COUNT , AVE , MIN
SELECT SALARY FROM WORKER GROUP BY SALARY ;

select dperatment, COUNT(deoartnemt) FROM worker group by department;
//without ading count(aggrigate) it act simply like DISTINCT

//find ave salary per department ? 
--AVE
select department, AVE(salery) FROM worker group by department ;
//apfter applying min/max/totl(sum) aggrigation you can find min salary
14. HAVING
//count department having more than two employes?
//having is use for filtering row from a group and work in group by 
--GROUP BY HAVING 
selcet department, COUNT(department) FROM Weorker group by department HAVING COUNT(departemnt) > 1;

//DIFFERENCE B/W WHERE AND HAVING
HAVING IS USE AFTER GROUP BY WHILE WHERE IS USE BEFIRE GROUP BY
GROUP BY IS NECCESSERY WITH HAHVING 
WHERE IS USE FOR UPDATE , SELECT AMD DELETE

//DDL CONSTRAIN

 1.PRIMARY KEY -----
 2.FOREGIN KEY -- IT REFERS PK OF SOMEOTHER TABLE
Creat table order(
Id int primery key,
delivery_date date,
FOREGIN KEY (CUST-ID) REFERENCES CUSTOMER(ID)
);
3.UNIQUE SYNTEX + CHECK (126)
creat taBle account(
id int primary key ,
name VARCHAR(255) UNIQUE ,
BALANCED INT 
CONSTRIANT acc_balance_chk CHECK(balance >10000)
);

INSERT INTO account(id , name , balance)
values(1 , 'A' , 10000);

select * from account ;
DROP TABLE ACCOUNT ;

4. DEFAULT 
CREAT TABLE ACCOUNT(
ID INT PEIMARY KEY ,
NAME VARCHAR(255);
BALANCE INT NOT NULL DEFAULT 
);

ATTRIBUTE CAN BE PK AND FK BOTH


--ADD NEW COLOUM 
ALTER TABLE account ADD intrest FLOAT NOT NULL DEFAULT 0;

--MODIFY
ALTER TABLE account MODIFY intrest DOUBLE NOT NULL DEFAULT 0;

--CHANGE COLOUM 
ALTER TABLE ACCOUNT CHANGE COLOUM INTREST SAVING_INTREST FLOAT NOT NULL DEFAULT 0;

--DROP COLOUM
ALTER TABLE ACCOUNT DROP COLOUM SAVING_INTREST;

 --RENAME
 ALTER TABLE ACCOUNT RENAME TO NEW_ACCOUNT;
DESC account ;(use to discribe the table)


DML

CREAT DATABASE TEMP ;
SHOW TEMP ;
USE TEMP ;

CREAT TABLE CUSTOMER(
ID INT PRIMARY KEY ,
CNAME VARCHAR(255),
ADDRESS VARCHAR(255),
GENDER VARCHAR(24),
CITY VARCHAR(25),
PINCODE INT(25)
);
SLECTE * FROM CUSTOMER ;

INSERT INTO CUSTOMER (ID , CNAME , ADDRESS , GENDER , CITY , PIMCODE)
VALUE ( 1234 , 'NIDHI' , 'BUXAR' , 'FEMLAE' , 'BUXAR' , ' 200211' ) ;
1. INSERT

INSERT INTO CUSTOMER (ID , CNAME )
VALUES(2345  , 'NIYA');

2. UPDATE
   UPDATE CUSTOMER SET ADDRESS = 'MUMBAI' , GENDER = 'MALE' WHERE ID = 121 ;
   //UPDATE MULTIPLE ROWS
   SET SQL_SAFE_UPDATE = 0;
   UPDATE CUSTOMER SET INT PINCODE = 1101 ;

3. DELETE
   DELETE FROM CUSTOMER ;
