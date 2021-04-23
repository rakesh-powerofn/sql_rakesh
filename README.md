# sql_rakesh
use case answers
1. Create table Customers,Agent and Orders. Use primary key for each tables and foreign keys for connecting the tables.Use Comments while creating the tables.
Ans -create table agent(agent_code char(4) primary key,agent_name varchar(25),country varchar(20),phone_no int unsigned, status int not null);
    -create table customer(cust_code char(4) primary key,cust_name varchar(25),cust_city varchar(20),phone_no int unsigned,agent_code char(4), FOREIGN KEY(agent_code) references agent(agent_code));
    -insert into customer values('C003','Archana','Banglore',945230981,'A004');
 
Inserting comments:
--Single line comment
/*The following table has a foreign key
Referencing AGENT table*/

 2. Alter the table agent , Add a new Column called "Commission".
 Ans -alter table agent add Commission decimal(3,2);
     -update agent set Commission='0.2' where agent_code='A001';
 
 3. Delete the column Phone_No from the agents table.
 Ans -alter table agent drop phone_no;
 
 4. Rename the Column "Commision" as "Commision_Percentage".
 Ans -alter table agent change Commission Commission_Percentage decimal(3,2);
 
 5. Make a copy of agent table with a table name as "AGENT_DETAILS" and delete the old agent table with the name "AGENT" 
 Ans -create table agent_details as select * from agent;
 
 6. Delete all the order table records in a single command. 
 Ans -truncate orders;
 
 7. Alter the tables orders and set a default value for the column Amount.
 Ans -alter table orders alter amount set default '10000';
