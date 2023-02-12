<a name="readme-top"></a>

<br />
<div align="center">
    <img src="https://avatars.githubusercontent.com/u/121735588?v=4" alt="Logo" width="200" height="200">


  <h3 align="center">Welcome to My Portfolio</h3>

  <p align="center">
    All my code :computer: , visuals :bar_chart: , and projects :chart_with_upwards_trend: are listed here.
    <br />
    <br />
    <a href="#SQL-Queries" target="_blank">SQL Queries</a>
    :small_blue_diamond:
    <a href="#Data-Analysis" target="_blank">Data Visuals</a>
    :small_blue_diamond:
    <a href="#Programming" target="_blank">Programming Code</a>
    <br>
    <sub><a href="#Contact">:wavy_dash: Contact Info :wavy_dash:</a></sub>
<br>
    <br>
<a href="https://github.com/CameronCSS"><strong><sub>« View Github Profile</sub></strong></a>
  </p>
</div>


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
    <ul>
    <li><a href="#SQL-Queries">SQL Queries</a></li>
    <ul><li>SQL Experience</li></ul>
    <ul><li>SQL Query Sample</li></ul>
    <br>
    <li><a href="#Data-Analysis">Data Analysis / Visuals</a></li>
    <ul><li>Analysis Experience</li></ul>
    <ul><li>Sales Report Visualization sample</li></ul>
    <br>
    <li><a href="#Programming">Programming languages / Code</a></li>
    <ul><li>Programming Experience</li></ul>
    <ul><li>Python code sample</li></ul>
    <br>
    <li><a href="#About">About Me</a></li>
    <li><a href="#Contact">Contact</a></li>
    <li><a href="#Contact">Resume</a></li>
    </ul>
</details>


<a name="SQL-Queries"></a>
# SQL Queries
	

#### :arrow_forward:<a href="https://github.com/CameronCSS/SQL-Queries/blob/main/README.md"> View all my SQL Projects</a>


----

<details open> 
<summary>SQL Query sample</summary>

#### The Question
```
In the first week after a customer joins 
the member points program (including their join date) 
they earn 2x points on all items, not just sushi - 
how many points do customer A and B have at the end of January?
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
_Full project_ :arrow_right:
<a href="https://github.com/CameronCSS/SQL-Queries/tree/main/8%20Week%20SQL%20Challenge%20%23%201" target="new">_"8 Week SQL Challenge #1"_</a>
</details>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

----
<a name="Data-Analysis"></a>
# Data Analysis / Visuals

#### :arrow_forward:<a href="https://github.com/CameronCSS/Data-Analysis/blob/main/README.md"> View all my Data Projects</a>

----

<details open>
<summary>Sales Report Visualization sample</summary>
	<br>
  :small_blue_diamond: Created a dashboard for a fictional manager using the Adventure Works sample database, which involved restoring the database, identifying data needs, cleaning and transforming the data, and importing it into Power BI.
<br>
<br>I broke down the entire process of building the Dashboard from scratch by restoring the database, identifying data needs, cleaning and transforming the data, building the dashboard with a pleasing number of visuals, and publishing the final product to Power BI services.
<br>
<br>
:arrow_right: View the <a href ="https://github.com/CameronCSS/Data-Analysis/blob/main/Power-BI-Dashboards/AdventureWorks/README.md">Full Process Breakdown</a>
    <br>
    <br>
:arrow_right: View the <a href ="https://app.powerbi.com/reportEmbed?reportId=b0fcfc95-aa85-4802-b47f-7e0fb300a481&autoAuth=true&ctid=ac060c52-a55a-40ca-9f98-cef91bfc7881">Sales Report</a> on Power BI Web services. <sub><sup>*You will need to sign in to Power BI</sub></sup>
<br>
  :heavy_minus_sign: 
  <br>
  [Dashboard Preivew] :arrow_heading_down:
  <br>
  <br>
  
  ![image](https://user-images.githubusercontent.com/121735588/216891607-ff81e7a6-bf0b-4e6a-9531-7898513d155d.png)


</details>
	
<p align="right">(<a href="#readme-top">back to top</a>)</p>
    
----
 <a name="Programming"></a>  
# Programming languages / Code

#### :arrow_forward:<a href="https://github.com/CameronCSS/Programming-Languages/blob/main/README.md"> View all my Programming Projects</a>

----
	
<details open>
<br>
<summary>Python code sample</summary>

:small_blue_diamond: A Simple Python code that Creates a UI and then calculates your Wages/Bills

[ Demonstration ] :arrow_heading_down:
 <br>
 <br>


![wage-calculator (3)](https://user-images.githubusercontent.com/121735588/211175350-f105e7f0-e049-4288-925c-4c9c8fa92d97.gif)


_Full project_ :arrow_right: <a href="https://github.com/CameronCSS/Programming-Languages/tree/main/Python%20Wage%20Calculator" target="new">Python Wage Calculator</a>

</details>

<p align="right">(<a href="#readme-top">back to top</a>)</p>
    
  -------
  
<a name="About"></a>  
## About Me

Strong problem solver, ability to identify and analyze complex issues, self motivated, endlessly looking to improve. My goal is to utilize my skills in SQL, Power BI, Tableau, and Python to turn complex data sets into easy to understand visuals that get everyone interested in the insights.

Currently seeking new opportunities. <li><a href="#Contact">Contact Me</a></li>

----

<h3 align="left">Languages and Tools:</h3>

<img src="https://user-images.githubusercontent.com/121735588/215948404-4d1bd4c2-0758-46bf-bc08-52e78f0b4bc8.PNG" width="300">

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=CameronCSS&layout=compact&theme=transparent&langs_count=6)](https://cameroncss.com)
<br>
![Cameron's GitHub stats](https://github-readme-stats.vercel.app/api?username=CameronCSS&show_icons=true&theme=transparent&hide=issues,contribs)

<a name="Contact"></a> 
## Contact Me

<div style="display: flex;">
  <table style="flex: 1;">
  
||
| --- |
| <a href="mailto:CameronSeamons@gmail.com">![gmail icon](https://user-images.githubusercontent.com/121735588/216516513-1bd223b5-89d4-4d02-860e-b132c18c47d9.png):heavy_minus_sign: CameronSeamons@gmail.com |
| <a href="https://www.linkedin.com/in/cameron-css/">![linkedin](https://user-images.githubusercontent.com/121735588/215363352-ad51a5e1-0de8-48be-8ceb-28c610e5d34d.png)</a> :heavy_minus_sign: https://www.linkedin.com/in/cameron-css/|
| <a href="https://twitter.com/Cameron_CSS">![twitter logo](https://user-images.githubusercontent.com/121735588/215363444-e4b080b6-e122-49cb-8b41-601dab6e10eb.png)</a> :heavy_minus_sign: https://twitter.com/Cameron_CSS |

  </table>
  <p style="margin-left: auto;">
    <a href="https://drive.google.com/file/d/19vkbf2HjEpXpxndWYa4A6Dyt6gsnGv73/view?usp=sharing" target="_blank" rel="noopener noreferrer">
      <img src="https://user-images.githubusercontent.com/121735588/215364205-abdfc0ac-53db-4733-8d43-b57c1bafb802.png" alt="Resume button">
    </a>
  </p>
</div>


<p align="right">(<a href="#readme-top">back to top</a>)</p>
