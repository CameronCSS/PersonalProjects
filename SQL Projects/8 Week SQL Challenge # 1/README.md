<a href="https://8weeksqlchallenge.com/case-study-1/" target="_blank"> LINK TO THE CHALLENGE </a>

## Introduction
Danny seriously loves Japanese food so in the beginning of 2021, he decides to embark upon a risky venture and opens up a cute little restaurant that sells his 3 favourite foods: sushi, curry and ramen.

![image](https://user-images.githubusercontent.com/121735588/211134729-5cd5bd4d-8420-4f0e-af9e-d77394265056.png)


Danny’s Diner is in need of your assistance to help the restaurant stay afloat - the restaurant has captured some very basic data from their few months of operation but have no idea how to use their data to help them run the business.

--
### Problem Statement
Danny wants to use the data to answer a few simple questions about his customers, especially about their visiting patterns, how much money they’ve spent and also which menu items are their favourite. Having this deeper connection with his customers will help him deliver a better and more personalised experience for his loyal customers.

----

#### Danny's Diner Data
```python
CREATE TABLE sales (
  "customer_id" VARCHAR(1),
  "order_date" DATE,
  "product_id" INTEGER
);

INSERT INTO sales
  ("customer_id", "order_date", "product_id")
VALUES
  ('A', '2021-01-01', '1'),
  ('A', '2021-01-01', '2'),
  ('A', '2021-01-07', '2'),
  ('A', '2021-01-10', '3'),
  ('A', '2021-01-11', '3'),
  ('A', '2021-01-11', '3'),
  ('B', '2021-01-01', '2'),
  ('B', '2021-01-02', '2'),
  ('B', '2021-01-04', '1'),
  ('B', '2021-01-11', '1'),
  ('B', '2021-01-16', '3'),
  ('B', '2021-02-01', '3'),
  ('C', '2021-01-01', '3'),
  ('C', '2021-01-01', '3'),
  ('C', '2021-01-07', '3');
 

CREATE TABLE menu (
  "product_id" INTEGER,
  "product_name" VARCHAR(5),
  "price" INTEGER
);

INSERT INTO menu
  ("product_id", "product_name", "price")
VALUES
  ('1', 'sushi', '10'),
  ('2', 'curry', '15'),
  ('3', 'ramen', '12');
  

CREATE TABLE members (
  "customer_id" VARCHAR(1),
  "join_date" DATE
);

INSERT INTO members
  ("customer_id", "join_date")
VALUES
  ('A', '2021-01-07'),
  ('B', '2021-01-09');

```
----
#### Questions

  - What is the total amount each customer spent at the restaurant?
  - How many days has each customer visited the restaurant?
  - What was the first item from the menu purchased by each customer?
  - What is the most purchased item on the menu and how many times was it purchased by all customers?
  - Which item was the most popular for each customer?
  - Which item was purchased first by the customer after they became a member?
  - Which item was purchased just before the customer became a member?
  - What is the total items and amount spent for each member before they became a member?
  - If each $1 spent equates to 10 points and sushi has a 2x points multiplier - how many points would each customer have?
  - In the first week after a customer joins the program (including their join date) they earn 2x points on all items, not just sushi
  - how many points do customer A and B have at the end of January?
  
----

#### Answers

  - What is the total amount each customer spent at the restaurant?

```python
SELECT customer_id, SUM(price) AS total_spent
  FROM sales
JOIN menu ON sales.product_id = menu.product_id
  GROUP BY customer_id
```
```
-- This query will join the sales and menu tables on the product_id column
-- The SUM() function is used to calculate the total amount spent by each customer.
-- The resulting table will have two columns: customer_id and total_spent.
-- We group the results by customer_id.
```
  - How many days has each customer visited the restaurant?

```

```
  - What was the first item from the menu purchased by each customer?
  - What is the most purchased item on the menu and how many times was it purchased by all customers?
  - Which item was the most popular for each customer?
  - Which item was purchased first by the customer after they became a member?
  - Which item was purchased just before the customer became a member?
  - What is the total items and amount spent for each member before they became a member?
  - If each $1 spent equates to 10 points and sushi has a 2x points multiplier - how many points would each customer have?
  - In the first week after a customer joins the program (including their join date) they earn 2x points on all items, not just sushi
  - how many points do customer A and B have at the end of January?


| Contact Method | Link |
| --- | --- |
| Email | CameronSeamons@gmail.com |
| LinkedIn | https://www.linkedin.com/in/cameron-css/|
| Twitter | https://twitter.com/Cameron_CSS |


### <a href="https://github.com/CameronCSS/PersonalProjects">Back to Index</a>
