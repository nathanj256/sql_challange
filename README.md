# sql_challange
nathan_johsson
CREATE TABLE "departments" (
  "dept_no" varchar,
  "dept_name" varchar
);

CREATE TABLE "department_employees" (
  "emp_no" VARCHAR,
  "dept_no" varchar
);

CREATE TABLE "employees" (
  "emp_no" varchar,
  "emp_title_id" varchar,
  "firt_date" date,
  "first_Name" varchar,
  "last_Name" varchar,
  "sex" varchar(20),
  "hire_date" date
);

CREATE TABLE "Salary" (
  "emp_no" VARCHAR,
  "Salary" int
);

CREATE TABLE "department_manager" (
  "emp_no" VARCHAR,
  "dept_no" int
);

CREATE TABLE "titles" (
  "title_id" int,
  "title" varchar
);

ALTER TABLE "department_employees" ADD FOREIGN KEY ("emp_no") REFERENCES "departments" ("dept_no");

ALTER TABLE "employees" ADD FOREIGN KEY ("emp_no") REFERENCES "department_employees" ("emp_no");

ALTER TABLE "Salary" ADD FOREIGN KEY ("emp_no") REFERENCES "employees" ("emp_no");

ALTER TABLE "titles" ADD FOREIGN KEY ("title_id") REFERENCES "employees" ("emp_title_id");

ALTER TABLE "departments" ADD FOREIGN KEY ("dept_no") REFERENCES "department_manager" ("dept_no");

ALTER TABLE "department_manager" ADD FOREIGN KEY ("emp_no") REFERENCES "Salary" ("emp_no");

ALTER TABLE "employees" ADD FOREIGN KEY ("emp_no") REFERENCES "employees" ("first_Name");

