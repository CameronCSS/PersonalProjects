<a name="readme-top"></a>

<br />
<div align="center">
    <img src="https://avatars.githubusercontent.com/u/121735588?v=4" alt="Logo" width="200" height="200">
	<br><a href="https://github.com/CameronCSS"><strong><sub>« View Github Profile</sub></strong></a>


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
    <ul><li>Data Visualization sample</li></ul>
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
<summary>Data Visualization sample</summary>
	<br>
  :small_blue_diamond: This dashboard was built with Tableau public using public Netflix date up to 2020.
    <br>
    <br>
    
[![Netflix](https://user-images.githubusercontent.com/121735588/215313601-be1ab656-af52-49a0-86a4-2b1a42910aec.png)](https://cameroncss.github.io/Data-Analysis/Netflix/index.html)



_Full project_ :arrow_right: <a href="https://cameroncss.github.io/Data-Analysis/Netflix/index.html" target="new">_Netflix Movies and TV Shows_</a>
   <br>
        <sub>_*Click for full interactive dashboard_</sub>
    <br>
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

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=CameronCSS&layout=compact&theme=transparent&langs_count=6)](https://cameroncss.github.io/)
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
