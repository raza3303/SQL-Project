# SQL-Project
Q1: Who is the senior most employee based on job title?
select *
from employee
order by levels desc
limit 1

Q2: Which countries have the most Invoices? 
select billing_country,count(billing_city) as invoice_count
from invoice
group by billing_country
order by invoice_count desc
limit 1

Q3: What are top 3 values of total invoice?
select total
from invoice
order by total desc
limit 3

Q4: Which city has the best customers? We would like to throw a promotional Music Festival in the city we made the most money. 
Write a query that returns one city that has the highest sum of invoice totals. 
Return both the city name & sum of all invoice totals

select billing_city,sum(total) as total_amt
from invoice
group by billing_city
order by total_amt desc
limit 1

Q5: Who is the best customer? The customer who has spent the most money will be declared the best customer. 
Write a query that returns the person who has spent the most money.

select c.first_name,c.last_name,sum(i.total) as total_amt
from customer as c
join invoice as i
on i.customer_id = c.customer_id
group by c.customer_id
order by total_amt desc
limit 1








