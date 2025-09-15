---
date: 2021-01-09 05:20:35 +0300
draft: false
title: Netflix Content Analysis – PostgreSQL & SQL
subtitle: Performed PostgreSQL analysis to uncover genre distribution and country-level trends in Netflix content.
tags: [SQL, PostgreSQL]
image: '/images/netflix_logo.png'
demo_url: ''
repo_url: 'https://github.com/Itsaakashgupta/netflix_project'
seo:
  page_description: 
  canonical_url: 
  featured_image: 
  author_twitter_handle: 
  open_graph_type:
  no_index: false
---

# Netflix Movies and TV Shows Data Analysis using SQL

- Analyzed over 6,000 Netflix titles using PostgreSQL to identify content trends by genre, 
release year, and country.  
- Identified significant shifts in original content production and key global content hubs, 
delivering actionable business insights through the use of joins, CTEs, and aggregations.

## Overview

This Project involves a comprehensive analysis of Netflix's movies and TV Shows data using SQL. The is to extract various valuable insights
and answers various business questions based on the dataset. The following  README provides a detailed of the project's objectives, business 
problems, solutions.

## Objective

1. Analyze the distribution of content type (Movies vs TV Shows).
2. Identify the most common ratings for movies and TV shows.
3. List and analyze content based on release years, countries, and durations.
4. Explore and categorize content based on specific criteria and keywords.

## Dataset

The data for the project is sourced from the Kaggle dataset - [Movies Dataset](https://www.kaggle.com/datasets/rahulvyasm/netflix-movies-and-tv-shows)
> **Download** - [netflix_csv](/uploads/netflix_titles.csv)

## Schema

```sql
Create Table netflix
(
	show_id	Varchar(6),
	type Varchar(10),
	title Varchar(150),
	director Varchar(250),
	casts Varchar(1000),
	country Varchar(150),
	date_added Varchar(150),
	release_year INT,
	rating Varchar(250),
	duration Varchar(250),
	listed_in Varchar(100),
	description Varchar(250)
)
```
## Business Problem and Solutions

### 1. Count the number of Movies vs TV Shows

```sql
Select
   type,
   Count(*)
From netflix
Group By type
```

### 2. Find the most common rating for movies and Tv shows


```sql
Select
  type,
  rating
From
(
	Select 
	     type,
		 rating,
		 Count(*) as total_content,
		 Rank() Over(Partition By type order By Count(*) Desc) as ranking 
	From netflix
	Group By 1,2
	--Order By 1,3 Desc
) As t1
Where ranking = 1
```

### 3. List all Movies released in a specific year(e.g. 2020)

```sql
Select 
  *
From netflix 
Where type= 'Movie'
      And
	  release_year = 2020
```

### 4. Find the top 5 countries with the most content on Netflix

```sql
Select
   unnest(String_To_Array(country,',')) as new_country,
   count(show_id) as total_content
From netflix
Group By 1
Order By 2 Desc
Limit 5
```

### 5. Identify the longest Movie

```sql
Select *
From netflix
Where type = 'Movie'
       And
	   duration = (select max(duration) From netflix)
```

### 6. Find the content added in the last Five Year

```sql
Select *
From netflix
Where 
   To_date(date_added, 'Month DD, YYYY') >= Current_Date - Interval '5 Year'
```

### 7. Find all Movies/Tv shows by director 'Rajiv Chilaka'

```sql
Select *
From netflix
Where director ILIKE '%Rajiv Chilaka%'
```

### 8. List all the Tv shows with more than 5 seasons

```sql
Select *
From netflix
Where type = 'TV Show'
      And
	  Split_Part(duration, ' ' , 1) :: numeric>5
```

### 9. Count the number of content items in each genre

```sql
Select 
    Unnest(String_to_Array(listed_in, ',')) as genre,
	count(show_id) as total_content
From netflix
Group By 1
Order By 2 Desc
```

### 10. List all movies that are documentaries

```sql
Select *
From netflix
Where listed_in ILIKE '%documentaries%'
```

### 11. Find all the content without directors

```sql
Select *
From netflix
Where director IS NULL
```

### 12. Find how many Movies actor 'Salman Khan' appeared in last 10 years

```sql
Select *
From netflix
Where 
    casts ILIKE '%Salman Khan%'
	And
	release_year > Extract(year From Current_date) - 10
```

### 13. Find the top 10 actors who have appeared in the highest number of Movies produced in India

```sql
Select
     Unnest(String_to_Array(Casts,',')) as actors,
	 Count(show_id) as total_content
From netflix
Where country ILIKE '%India%'
Group By 1
Order By 2 DESC
LIMIT 10
```

### 14. Categorize the content based on the presence of the keywords 'Kill' and 'Violence' in the description field.
### Label content containing those keyword as 'Bad' and all content as 'Good'. Count how many items fall into each category

```sql
With new_table
AS
	(Select *,
	      Case 
		    When 
			   description ILIKE '%Kill%'
			  Or description ILIKE '%Violence%'
			 Then 'Bad content'
			 Else 'Good Content'
			 End category
	From netflix)
Select 
    category,
	count(*) as total_content
From new_table
Group By 1
```