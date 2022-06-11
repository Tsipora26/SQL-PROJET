# SQL-PROJET
CREATE TABLE Employees
(
  Employees_Id NUMERIC(10) NOT NULL,
  Employee_Name VARCHAR(15) NOT NULL,
  Salary NUMERIC(5) NOT NULL,
  hire_year NUMERIC(4) NOT NULL,
  Address VARCHAR(40) NOT NULL,
  PRIMARY KEY (Employees_Id)
);

CREATE TABLE Card
(
  Number_Card NUMERIC(16) NOT NULL,
  Valid VARCHAR(10) NOT NULL,
  Credit_Card_Type VARCHAR(15) NOT NULL,
  PRIMARY KEY (Number_Card)
);

CREATE TABLE Visitor
(
  gender VARCHAR(10) NOT NULL,
  age NUMERIC(2) NOT NULL,
  visitor_id VARCHAR(10) NOT NULL,
  name_visitor VARCHAR(20) NOT NULL,
  Number_Card NUMERIC(16) NOT NULL,
  PRIMARY KEY (visitor_id),
  FOREIGN KEY (Number_Card) REFERENCES Card(Number_Card)
);

CREATE TABLE Event
(
  date DATE NOT NULL,
  sort VARCHAR(20) NOT NULL,
  price NUMERIC(5) NOT NULL,
  City VARCHAR(15) NOT NULL,
  visitor_id VARCHAR(10) NOT NULL,
  Employees_Id NUMERIC(10) NOT NULL,
  PRIMARY KEY (date),
  FOREIGN KEY (visitor_id) REFERENCES Visitor(visitor_id),
  FOREIGN KEY (Employees_Id) REFERENCES Employees(Employees_Id)
);




