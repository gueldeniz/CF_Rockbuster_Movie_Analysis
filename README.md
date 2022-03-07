# Rockbuster-movies-analysis

In this project, I worked as a junior data analyst for the mock movie company Rockbuster Stealth LLC.

## Information
Rockbuster Stealth LLC i s a movie rental company that used to have stores around the world. Due to stiff competition from streaming services such as Netflix and Amazon Prime, the Rockbuster Stealth management team i s planning to use i ts existing movie licenses to launch an online video rental service in order to stay competitive.

During this project, I have loaded Rockbuster’s data into a relational database management system (RDBMS) and used SQL to analyze the data and answer any ad-hoc business questions that BI and marketing departments needed.

## Key Questions and Objectives
I answered all the business questions for Rockbuster Stealth LLC and made suggestions for new  marketing strategies.

- Which movies contributed the most/least to revenue gain?
- What was the average rental duration for all videos?
- Which countries are Rockbuster customers based i n?
- Where are customers with a high l ifetime value based?
- Do sales figures vary between geographic regions?


## Achievements

- Explored how data is structured in a relational database
- Learned writing complex queries, as well as, subqueries and CTEs
- Added SQL techniques to my toolbox for data analysis
- Answered business questions by using SQL
- Created data dictionary
- Used Tableau to build dashboards
- Communicated results to stakeholder

## SQL Query example with CTE

	WITH average_cte AS 
	(SELECT  A. customer_id,
	B. first_name AS customer_first_name,
	B. last_name AS customer_last_name,
	D.city,E. country,
	SUM (amount) AS total_amount_paid
	FROM payment A
	INNER JOIN customer B ON A.customer_id = B.customer_id
	INNER JOIN address C ON B.address_id = C.address_id
	INNER JOIN city D ON C.city_id = D.city_id
	INNER JOIN country E ON D.country_id = E.country_id
	AND city IN ('Aurora','Tokat','Tarsus','Atlixco','Emeishan','Pontianak','Shimoga','Aparecida de Goinia','Zalantun','Taguig')
	GROUP BY A.customer_id, B.first_name, B.last_name, D.city, E.country
	ORDER BY total_amount_paid DESC
	LIMIT 5) 
	SELECT AVG (total_amount_paid) AS average_amount_paid
	FROM average_cte
	
## Presentation


