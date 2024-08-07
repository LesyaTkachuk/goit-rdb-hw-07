USE mydb;

-- select year, month and day from datetime attribute
SELECT id, date, YEAR(date) as year, MONTH(date) as month, DAY(date) as day FROM orders; 

-- select date and add extra day to it
SELECT id, date, date + INTERVAL 1 DAY as plus_day FROM orders; 

-- select date and correspondent UNIX time 
SELECT id, date, UNIX_TIMESTAMP(date) as unix_time FROM orders;

-- count number of rows in date range
SELECT COUNT(*) FROM orders 
WHERE date BETWEEN '1996-07-10 00:00:00' AND '1996-10-08 00:00:00';

--  select id and date in JSON formatt
SELECT id, date, JSON_OBJECT('id', id, 'date', date) as json_data FROM orders;

