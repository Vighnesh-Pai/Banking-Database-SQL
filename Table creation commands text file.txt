
DROP TABLE customer CASCADE CONSTRAINTS;
DROP TABLE employee CASCADE CONSTRAINTS;
DROP TABLE accounts CASCADE CONSTRAINTS;
DROP TABLE loan_account CASCADE CONSTRAINTS;
DROP TABLE transactions CASCADE CONSTRAINTS;
DROP TABLE customer_has_accounts CASCADE CONSTRAINTS;
DROP TABLE d_loan_acc CASCADE CONSTRAINTS;


create table customer
(
        cust_id int primary key,
        first_name varchar(100),
        middle_name varchar(100),
        last_name varchar(100),
        gender varchar(100),
        email varchar(100),
        contact varchar(100),
        street varchar(100),
        city varchar(100),
        state varchar(100),
        pin int,
        pan_no varchar(100),
        nationality varchar(100)
);
create table employee
(
        emp_id int primary key,
        username varchar(100),
        password varchar(100),
        first_name varchar(100),
        middle_name varchar(100),
        last_name varchar(100),
        designation varchar(100),
        contact varchar(100),
        gender varchar(100),
        street varchar(100),
        city varchar(100),
        state varchar(100),
        pin int,
        email varchar(100),
        salary float,
        nationality varchar(100),
        age int        
);
create table accounts
(
        acc_no int primary key,
        AEemp_id int,
        acc_type varchar(100),
        open_date date,
        close_date date,
        balance int,
        interest_amount float,
        
        foreign key(AEemp_id)references employee(emp_id)

);
create table loan_account
(
        loan_id int primary key,
        LCcust_id int,
        LEemp_id int,
        date_of_loan date,
        loan_type varchar(100), 
        duration int,
        total_amount int,
        status varchar(100),
        principle_amount int,
        interest float,
        foreign key(LCcust_id)references customer(cust_id),
        foreign key(LEemp_id)references employee(emp_id)
);
create table d_loan_acc
(
        d_loan_id int primary key,
        d_loan_type varchar(100), 
        d_duration int,
        d_total_amount int
);
create table transactions
(
        TCcust_id int,
        TEemp_id int,
        trans_id int primary key,
        date_of_trans date,
        trans_type varchar(100),
        amount int,
        total_balance int,
        foreign key(TCcust_id)references customer(cust_id),
        foreign key(TEemp_id)references employee(emp_id)
);

create table customer_has_accounts
(
        CAcust_id int,
        CAacc_no int,
        primary key(CAcust_id,CAacc_no),
        foreign key(CAcust_id) references customer(cust_id),
        foreign key(CAacc_no) references accounts(acc_no)

);


insert into customer values(101,'Neil','Aryan','Singh','Male','neils@gmail.com','9123373212','82,Sirish Society, Radhika Chowk','Jabalpur','Madhya Pradesh',3707,'ALWPG5809L','India');
insert into customer values(102,'Shlok','Kumar','Jha','Male','muthi@gmail.com','8821000990','71,Saket Nagar','Bhopal','Madhya Pradesh',2043,'LAWPG582A9','India');
insert into customer values(103,'Ram','Prasad','Sharma','Male','ramps@gmail.com','7898291878','97,Danish Chowk','Wasseypur','Jharkhand',4505,'ALWPGZ876L','India');
insert into customer values(104,'Aditi','Rao','Hadari','Female','aditirh@gmail.com','6267947218','31,Gulmohar City Society','Panchkula','Haryana',3087,'WPWPG5809P','India');
insert into customer values(105,'Aishwarya','Rai','Bacchan','Female','aishsalman@gmail.com','9785004056','012,Mahendra Nagar','Patna','Bihar',6902,'SPWPG5809A','India');
insert into customer values(106,'Atal','Kumar','Seth','Male','atal@gmail.com','9123373465','75,Sirish Society, Radhika Chowk','Bhopal','Madhya Pradesh',3707,'ASDPG52345A','India');
insert into customer values(107,'Aman','Kumar','Banthia','Male','aman@gmail.com','8821001234','43,Saket Nagar','Bhopal','Madhya Pradesh',2043,'SQRPG582A9','India');
insert into customer values(108,'Pelpendicular','Ali','Khan','Male','pp@gmail.com','789829456','90,ATS Chowk','Bhopal','Jharkhand',4505,'DLQPGZ876L','India');
insert into customer values(109,'Tanjent','Ali','Khan','Male','tanjent@gmail.com','6267944567','421,Ashiana City Society','Bhopal','Haryana',3087,'CKWGG5809P','India');
insert into customer values(110,'Manish','Singh','Sisodia','Male','smidh@gmail.com','9785004324','124,Bhagat Nagar','Patna','Bihar',6902,'APLQG5809A','India');
insert into customer values(111,'Rama','Kumari','Devi','Female','rma@gmail.com','9123377890','820,Kajaria Society, Radhika Chowk','Bhopal','Madhya Pradesh',3707,'LQVPG5809L','India');
insert into customer values(112,'Shama','Parveen','Khan','Female','shama@gmail.com','8821001234','090,Saket Nagar','Bhopal','Madhya Pradesh',2043,'LAWPG5A981','India');
insert into customer values(113,'Alia','Bhatt','Kapoor','Female','alia@gmail.com','7898298635','124,Sameer Chowk','Wasseypur','Jharkhand',4505,'PQXPGZ876L','India');
insert into customer values(114,'Jigneesh','N','Pai','Male','jigneesh@gmail.com','6267941780','313,Jaya Nagar','Vasco','Goa',2365,'QPMRG5809P','India');
insert into customer values(115,'Vighnesh','N','Pai','Male','vighnesh@gmail.com','9785004124','313,Jaya Nagar','Vasco','Goa',2365,'LMSQG5809A','India');
insert into customer values(116,'Kartik','Aryan','Kumar','Male','kartik@gmail.com','9123378901','69,Manish Society, Radhika Chowk','Bhopal','Madhya Pradesh',3707,'LQDPG5809L','India');
insert into customer values(117,'Shah','Rukh','Khan','Male','srk@gmail.com','8821000481','12,Ram Nagar','Bhopal','Madhya Pradesh',2043,'LQAPG582A9','India');
insert into customer values(118,'Ramu','Prasad','Sharma','Male','ramu@gmail.com','7898293421','91,Shaheed Chowk','Panaji','Goa',4505,'ALQPGZ876L','India');
insert into customer values(119,'Kanika','Rao','Yadav','Female','kanika@gmail.com','6267947894','45,Railway City Society','Bhopal','Haryana',3087,'LQPDG5809P','India');
insert into customer values(120,'Ruby','Ali','Iqbal','Female','ruby@gmail.com','9785001278','045,Sameer Nagar','Patna','Bihar',6902,'KLQPG5809A','India');




insert into employee values(201,'Nitinsh','NsH#12','Nitin','Dev','Shukla','Branch Manager','9123521223','Male','#42,Silver Orchid ,Gandhinagar','Indore','Madhya Pradesh',4526,'nitinsh@gmail.com',28000,'India',32);
insert into employee values(202,'Sunny','Sny29','Sunny','Suresh','Jali','Internal Auditor','944898563','Female','#11,Bren Imperia ,Sarjapur','Bangalore','Karanataka',5600,'sunny@gmail.com',20000,'India',45);
insert into employee values(203,'Anish','Anh@34','Anish','Sam','Shah','Loan Officer','9731922345','Male','#23,Prestige Courtyards ,Sholinganallur','Chennai','Tamil Nadu',6001,'anish@gmail.com',45000,'India',28);
insert into employee values(204,'Arun','Arun#15','Arun','shiv','Patil','Bank Teller','7619200331','Male','#98,Cityspace ,Vidyanagar','Cochin','Kerala',5726,'arun@gmail.com',39000,'India',35);
insert into employee values(205,'Ranjit','Rnj@25','Ranjit','Sudesh','Deshpande','Data Processing Officer','9447634231','Male','#29,Jeevan Building,Jaynagar','Hubli','Karnataka',5600,'ranjit@gmail.com',43000,'Nepal',32);
insert into employee values(206,'Suresh','SsH#12','Suresh','Dev','Shukla','Loan Officer','9121126332','Male','#12,Silver Orchid ,Gandhinagar','Indore','Madhya Pradesh',4526,'suresh@gmail.com',100000,'India',36);
insert into employee values(207,'Sammy','Sam29','Sammy','Suresh','Sharma','Clerk','9128986213','Male','#89,Bren Imperia ,Sarjapur','Bangalore','Karanataka',5600,'sammy@gmail.com',34000,'India',39);
insert into employee values(208,'Ashish','Ash@34','Ashish','Kumar','Anshuman','Loan Officer','9671926482','Male','#98,Prestige Courtyards ,Sholinganallur','Chennai','Tamil Nadu',6001,'ashish@gmail.com',43000,'India',38);
insert into employee values(209,'Aruna','Aruna#15','Aruna','shiv','Jha','Clerk','7619200390','Female','#90,Cityspace ,Vidyanagar','Cochin','Kerala',5726,'aruna@gmail.com',76000,'India',42);
insert into employee values(210,'Ranjita','Rnja@25','Ranjita','Null','Pandey','Data Processing Officer','9907634231','Female','#44,Jeevan Tara Building,Jaynagar','Bangalore','Karnataka',56000,'ranjita@gmail.com',46000,'India',42);
insert into employee values(211,'Nikita','Nit#12','Nikita','Null','Sachan','Loan Officer','9123526332','Female','#41,Silver Orchid ,Gandhinagar','Indore','Madhya Pradesh',4526,'nikita@gmail.com',54000,'India',27);
insert into employee values(212,'Sammer','Same29','Sameer','Kumar','Leone','Clerk','9448986213','Male','#11,Bren Imperia ,Sarjapur','Bangalore','Karanataka',5600,'sameer@gmail.com',55000,'India',36);
insert into employee values(213,'Aman','Amn@34','Aman','singh','Banthia','Loan Officer','9731926482','Male','#13,Prestige Courtyards ,Sholinganallur','Chennai','Tamil Nadu',6001,'aman@gmail.com',34000,'India',31);
insert into employee values(214,'Vansh','vns#15','Vansh','shiv','Kapoor','Helper','7619200331','Male','#100,Cityspace ,Vidyanagar','Cochin','Kerala',5726,'vansh@gmail.com',67000,'India',33);
insert into employee values(215,'Ranjna','Rnjfs@25','Ranjna','Sudesh','Pandey','Data Processing Officer','9447634231','Female','#22,Jeevan Tara Building,Jaynagar','Bangalore','Karnataka',5600,'ranjna@gmail.com',55000,'India',29);
insert into employee values(216,'Neel','Ntn#12','Neel','Nitin','Mukesh','Clerk','9123526332','Male','#12,Silver Orchid ,Gandhinagar','Indore','Madhya Pradesh',4526,'neel@gmail.com',41000,'India',29);
insert into employee values(217,'Munny','Mny29','Munny','Null','Sharma','Gaurd','9448986213','Female','#69,Bren Imperia ,Sarjapur','Bangalore','Karanataka',5600,'munny@gmail.com',56000,'India',37);
insert into employee values(218,'Prakhar','Prk@34','Prakhar','Sam','Tripathi','Loan Officer','9731926482','Male','#56,Prestige Courtyards ,Sholinganallur','Chennai','Tamil Nadu',6001,'prakhar@gmail.com',35900,'India',45);
insert into employee values(219,'Arjun','Arjn#15','Arjun','shiv','Kapoor','Gaurd','7619200331','Male','#92,Cityspace ,Vidyanagar','Cochin','Kerala',5726,'prakhar@gmail.com',69000,'India',47);
insert into employee values(220,'Divit','dvt@25','Divit','Pratap','Singh','Data Processing Officer','9447634231','Male','#90,Jeevan Tara Building,Jaynagar','Bangalore','Karnataka',5600,'divit@gmail.com',70000,'India',54);


insert into accounts values(301,201,'Savings','20-10-1997','30-12-2019',450000,22500);
insert into accounts values(302,202,'Current','04-09-2005',Null,4500,225);
insert into accounts values(303,203,'Savings','10-12-1995','05-04-2020',100000,5000);
insert into accounts values(304,204,'Current','12-05-2015',Null,68000,3400);
insert into accounts values(305,205,'Savings','15-09-2001',Null,1200000,60000);
insert into accounts values(306,206,'Savings','10-09-1997','12-03-2021',470000,22500);
insert into accounts values(307,207,'Current','19-01-2008',Null,500,25);
insert into accounts values(308,208,'Savings','17-09-1985','15-04-2015',790000,5000);
insert into accounts values(309,209,'Current','11-07-2010',Null,340000,17000);
insert into accounts values(310,210,'Savings','15-09-2019',Null,150000,7500);
insert into accounts values(311,211,'Savings','20-10-1991','30-12-2020',450000,22500);
insert into accounts values(312,212,'Current','03-12-2009',Null,69000,3450);
insert into accounts values(313,213,'Savings','31-05-1995','12-02-2020',100000,5000);
insert into accounts values(314,214,'Current','12-05-2017',Null,435000,21750);
insert into accounts values(315,215,'Savings','15-09-2002',Null,24500,1225);
insert into accounts values(316,216,'Savings','20-10-1991','30-10-2015',450000,22500);
insert into accounts values(317,217,'Current','14-10-2007',Null,29500,1475);
insert into accounts values(318,218,'Savings','10-12-1982','05-03-2008',100000,5000);
insert into accounts values(319,219,'Current','19-04-2011',Null,100,5);
insert into accounts values(320,220,'Savings','14-10-2014',Null,375,18.75);

insert into transactions values(101,201,1111,'13-07-2012','Cash Transaction',25000,425000);
insert into transactions values(102,202,1112,'10-11-2021','Cash Transaction',100,4400);
insert into transactions values(103,203,1113,'18-03-2019','Debit Transaction',20000,80000);
insert into transactions values(104,204,1114,'11-10-2015','Cash Transaction',8000,60000);
insert into transactions values(105,205,1115,'05-12-2016','Credit Bill',200000,1000000);
insert into transactions values(106,206,1116,'04-09-2020','Cash Transaction',15000,455000);
insert into transactions values(107,207,1117,'02-03-2010','Debit Transaction',100,400);
insert into transactions values(108,208,1118,'07-11-2007','Credit Bill',90000,700000);
insert into transactions values(109,209,1119,'24-05-2012','Cash Transaction',5000,335000);
insert into transactions values(110,210,1120,'28-02-2021','Debit Transaction',10000,140000);


insert into loan_account values(401,101,201,'14-08-2012','Car Loan',5,350000,'Disapproved',150000,5);
insert into loan_account values(402,102,202,'19-10-2015','Home Loan',20,3000000,'Approved',2500000,6);
insert into loan_account values(403,103,203,'18-12-2019','Study Loan',4,400000,'Approved',300000,4);
insert into loan_account values(404,104,204,'04-11-2019','Office Loan',10,5000000,'Approved',3500000,4);
insert into loan_account values(405,105,205,'10-04-2021','Personal Loan',1,500000,'Approved',300000,5);
insert into loan_account values(406,106,206,'06-03-2020','Home Loan',21,2000000,'Disapproved',1500000,6);
insert into loan_account values(407,107,207,'07-07-2019','Personal Loan',2,400000,'Approved',350000,4);
insert into loan_account values(408,108,208,'18-05-2021','Car Loan',6,450000,'Approved',200000,5);  
insert into loan_account values(409,109,209,'29-03-2018','Study Loan',5,600000,'Approved',400000,4);
insert into loan_account values(410,110,210,'01-01-2017','Personal Loan',3,700000,'Disaproved',500000,5);

insert into customer_has_accounts values(101,301);
insert into customer_has_accounts values(102,301);
insert into customer_has_accounts values(101,302);
insert into customer_has_accounts values(102,302);


commit;