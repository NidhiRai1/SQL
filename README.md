# SQL
DBMS BASICS AT ONE PLACE 





---GROUP BY 
//IT USES FOR THE AGGRIGAIIN PUPOSES LIKE COURSES , COUNT , AVE , MIN
select dperatment from , COUNT(deoartnemt) worker group by department;
//without ading count(like nad aggrigate) it act simply like DISTINCT

//find ave salary per department ? 
--AVE
select department from, AVE(salery) worker group by department ;
//apfter applying min/max/totl(sum) aggrigation you can find min salary

//count department having more than two employes?
//having is use for filtering row from a group and work in group by 
--GROUP BY HAVING 
selcet department from, COUNT(department) eorker group by department HAVING COUNT(departemnt) > 2;

DDL 
 
Creat a table account
Id int primery key,
name VARCHAR(255) UNIQUE ,
BALANCED INT 
CONSTRIANT acc_balance_chk CHECK(balance >10000)
);

INSERT INTO account(id , name , balance)
values(1 , 'A' , 10000);

select * from account ;


--ADD NEW COLOUM 
ALTER TABLE account ADD intrest FLOAT NOT NULL DEFAULT 0;

--MODIFY
ALTER TABLE account MODIFY intrest DOUBLE NOT NULL DEFAULT 0;

DESC account ;(use to discribe the table)
