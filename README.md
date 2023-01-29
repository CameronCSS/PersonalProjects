<a name="readme-top"></a>

<br />
<div align="center">
    <img src="https://avatars.githubusercontent.com/u/121735588?v=4" alt="Logo" width="150" height="150">

  <h3 align="center">Welcome to My Portfolio</h3>

  <p align="center">
    All my code, visuals, and projects are listed here!
    <br />
      <br>
      <sub><sup>[ LINKS TO PROJECT FOLDERS ]</sup></sub>
    <br />
    <a href="https://github.com/CameronCSS/SQL-Queries" target="_blank">SQL Queries</a>
    ·
    <a href="https://github.com/CameronCSS/Data-Analysis" target="_blank">Data Visuals</a>
    ·
    <a href="https://github.com/CameronCSS/Programming-Languages" target="_blank">Programming Code</a>
    <br />
    <br />
    <br />
     <a href="https://github.com/CameronCSS"><strong>« Back to Profile</strong></a>
  </p>
</div>


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
    <ul>
    <li>SQL Queries</li>
    <ul><li><a href="#SQL-Experience">SQL Experience</a></li></ul>
    <br>
    <li>Data Analysis / Visuals</li>
    <ul><li><a href="#Analysis-Experience">Analysis Experience</a></li></ul>
    <br>
    <li>Programming languages / Code</li>
    <ul><li><a href="#Programming-Experience">Programming Experience</a></li></ul>
    <br>
    <li><a href="#Currently-working-on">Currently working on</a></li>
    <li><a href="#About">About Me</a></li>
    <li><a href="#Contact">Contact</a></li>
    </ul>
</details>


# PORTFOLIO

# SQL Queries
<details>
<summary>View Projects</summary>
<a href="https://github.com/CameronCSS/SQL-Queries/tree/main/8%20Week%20SQL%20Challenge%20%23%201" target="new">8 Week SQL Challenge # 1</a>
<br>
<a href="https://github.com/CameronCSS/SQL-Queries/tree/main/Khan%20Academy%20Advanced%20SQL" target="new">Khan Academy Advanced SQL</a>
<br>
<a href="https://github.com/CameronCSS/SQL-Queries/tree/main/SQLbolt%20-%20SQL%20lessons" target="new">SQLbolt - SQL lessons</a>
</details>

<a name="SQL-Experience"></a>
## SQL Experience


  - Google data analytics professional certificate
  - Completed Khan Academy - Intro to SQL Course
  - Finished the SQLBolt - Learn SQL Training
  - Case Study 'Data with Danny' 8 Week SQL Challenge

### SQL Query sample
----
_Full project »_
<a href="https://github.com/CameronCSS/SQL-Queries/tree/main/8%20Week%20SQL%20Challenge%20%23%201" target="new">"8 Week SQL Challenge #1"</a>

#### The Challenge
```
In the first week after a customer joins the member points program (including their join date) 
they earn 2x points on all items, not just sushi - how many points do customer A and B have at the end of January?
```

#### SQL Query
```sql
WITH dates AS 
(
 SELECT *, 
  DATEADD(DAY, 6, join_date) AS valid_date, 
  EOMONTH('2021-01-31') AS last_day
 FROM members
),
purchases AS (
  SELECT sales.customer_id, menu.product_name, menu.price, sales.order_date,
         members.join_date,
         (CASE
         WHEN menu.product_name = 'sushi' THEN 2 * menu.price
         WHEN sales.order_date BETWEEN members.join_date AND dates.valid_date THEN menu.price * 2
            ELSE menu.price
          END) * 10 AS points
  FROM sales
  JOIN menu ON sales.product_id = menu.product_id
  JOIN members ON sales.customer_id = members.customer_id
  JOIN dates ON members.customer_id = dates.customer_id
)
SELECT purchases.customer_id, SUM(points) as total_points
FROM purchases
JOIN dates ON purchases.customer_id = dates.customer_id
WHERE order_date < dates.last_day
GROUP BY purchases.customer_id;
```
<p align="right">(<a href="#readme-top">back to top</a>)</p>

----

# Data Analysis / Visuals
    
<details>
<summary>View Projects</summary>
<a href="https://cameroncss.github.io/Data-Analysis/Netflix/index.html" target="new">Netflix Movies and TV Shows</a><em> *Interactive Dashboard</em>
<br>
<a href="https://github.com/CameronCSS/Data-Analysis/tree/main/Sales%20Performance%20Review" target="new">Sales Performance Review</a>
<br>
<a href="https://github.com/CameronCSS/Data-Analysis/tree/main/SLC%20civilian%20complaints" target="new">SLC civilian complaints</a>
  <br>
  <br>
</details>
<a name="Analysis-Experience"></a>
## Analysis Experience

   - Power BI / Tableau Visual Reports
   - Case study and data breakdowns
   - API pulls and database building
   - Full analysis and reports on data
   - Buidling finished Dashboards
    
### Data Visualization sample
----
_Full project »_ <a href="https://cameroncss.github.io/Data-Analysis/Netflix/index.html" target="new">_Netflix Movies and TV Shows_</a>
   </br>
        <sub>_*Click link for full interactive dashboard_</sub>
    </br>
    </br>
![Netflix](https://user-images.githubusercontent.com/121735588/215313601-be1ab656-af52-49a0-86a4-2b1a42910aec.png)
<br>
<p align="right">(<a href="#readme-top">back to top</a>)</p>
    
----
   
# Programming languages / Code
 
<details>
<summary>View Projects</summary>
<a href="https://github.com/CameronCSS/Programming-Languages/tree/main/Python%20Wage%20Calculator" target="new">Python Wage Calculator</a>
</details>

<a name="Programming-Experience"></a>
## Programming Experience

  - Google data analytics professional certificate (*R) 
  - Completed Kaggle 'Intro to Programming' Course
  - Built out a few simple programs in Python through Self Learning
  - C# app building in High School
    
### Python code sample
----
    
_Full project »_ <a href="https://github.com/CameronCSS/Programming-Languages/tree/main/Python%20Wage%20Calculator" target="new">Python Wage Calculator</a>
    <br>
    <br>
    <br>
![wage-calculator (3)](https://user-images.githubusercontent.com/121735588/211175350-f105e7f0-e049-4288-925c-4c9c8fa92d97.gif)
 

    
![image](https://user-images.githubusercontent.com/121735588/215314444-6760ecf2-f427-4f02-9b26-3d1189549cc6.png)


    
<p align="right">(<a href="#readme-top">back to top</a>)</p>
    
  -------

<a name="Currently-working-on"></a>
## Currently working on

- 📝 I’m currently working on a report about <a href = "https://github.com/CameronCSS/Data-Analysis/tree/main/SLC%20Homless%20Data"> **SLC Homeless numbers </a> after shutting down Homeless Centers**
- 👉 Finishing up Week #2 of the <a href ="https://github.com/CameronCSS/SQL-Projects/tree/main/8%20Week%20SQL%20Challenge%20%23%201"> 8 Week SQL Challenge </a> with SQL query answer breakdowns.
- ⚡ Expanding my knowledge of Python and pandas library**
  
<a name="About"></a>  
## About Me

A passionate data analyst dedicated to uncovering valuable insights hidden within complex data sets. Strong problem solver, ability to identify and analyze complex issues, self motivated, endlessly looking to improve. My goal is to utilize my skills in SQL, Power BI, Tableau, and Python to turn complex data sets into easy to understand visuals that get everyone interested in the insights.

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://www.mysql.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" width="40" height="40"/> </a> <a href="https://www.postgresql.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="postgresql" width="40" height="40"/> </a> <a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> <a href="https://pandas.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/pandas/pandas-original.svg" alt="pandas" width="40" height="40"/> </a> <a href="https://www.photoshop.com/en" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg" alt="photoshop" width="40" height="40"/> </a> <a href="https://www.blender.org/" target="_blank" rel="noreferrer"> <img src="https://download.blender.org/branding/community/blender_community_badge_white.svg" alt="blender" width="40" height="40"/> </a> </p>

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=CameronCSS&layout=compact&theme=transparent&langs_count=6)](https://cameroncss.github.io/)
<br>
![Cameron's GitHub stats](https://github-readme-stats.vercel.app/api?username=CameronCSS&show_icons=true&theme=transparent&hide=issues,contribs)

<a name="Contact"></a> 
## Contact Me

| Contact Method | Link |
| --- | --- |
| Email | CameronSeamons@gmail.com |
| LinkedIn | https://www.linkedin.com/in/cameron-css/|
| Twitter | https://twitter.com/Cameron_CSS |
| Resume | ['Cameron Seamons' Resume](https://drive.google.com/file/d/19vkbf2HjEpXpxndWYa4A6Dyt6gsnGv73/view?usp=sharing) | 
<p align="right">(<a href="#readme-top">back to top</a>)</p>

