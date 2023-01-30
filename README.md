<a name="readme-top"></a>

<br />
<div align="center">
    <img src="https://avatars.githubusercontent.com/u/121735588?v=4" alt="Logo" width="150" height="150">

  <h3 align="center">Welcome to My Portfolio</h3>

  <p align="center">
    All my :computer: code, :bar_chart: visuals, and :chart_with_upwards_trend: projects are listed here!
    <br />
      <br>
      <sub><sup>[ PROJECT FOLDER LINKS ]</sup></sub>
    <br />
    <a href="https://github.com/CameronCSS/SQL-Queries" target="_blank">SQL Queries</a>
    :small_blue_diamond:
    <a href="https://github.com/CameronCSS/Data-Analysis" target="_blank">Data Visuals</a>
    :small_blue_diamond:
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
    <li><a href="#Currently-working-on">Currently working on</a></li>
    <li><a href="#About">About Me</a></li>
    <li><a href="#Contact">Contact</a></li>
    </ul>
</details>


# PROJECTS
<a name="SQL-Queries"></a>
# SQL Queries

<details>
<summary>View Projects</summary>
<a href="https://github.com/CameronCSS/SQL-Queries/tree/main/8%20Week%20SQL%20Challenge%20%23%201" target="new">8 Week SQL Challenge # 1</a>
<br>
<a href="https://github.com/CameronCSS/SQL-Queries/tree/main/Khan%20Academy%20Advanced%20SQL" target="new">Khan Academy Advanced SQL</a>
<br>
<a href="https://github.com/CameronCSS/SQL-Queries/tree/main/SQLbolt%20-%20SQL%20lessons" target="new">SQLbolt - SQL lessons</a>
</details>


## SQL Experience
:ballot_box_with_check: Google data analytics professional certificate
 <br> :ballot_box_with_check: Completed Khan Academy - Intro to SQL Course
 <br> :ballot_box_with_check: Finished the SQLBolt - Learn SQL Training
 <br> :ballot_box_with_check: Case Study 'Data with Danny' 8 Week SQL Challenge

### SQL Query sample
----

### [ Project Description ]

:small_blue_diamond: Danny's Diner wants to use data to answer a few simple questions about his customers.
<br> :small_blue_diamond: You need to use SQL queries to give him the answers to best help his business.


#### The Challenge
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
<p align="right">(<a href="#readme-top">back to top</a>)</p>

----
<a name="Data-Analysis"></a>
# Data Analysis / Visuals
    
<details>
<summary>View Projects</summary>
<a href="https://cameroncss.github.io/Data-Analysis/Netflix/index.html" target="new">Netflix Movies and TV Shows</a>
<br>
<a href="https://github.com/CameronCSS/Data-Analysis/tree/main/Sales%20Performance%20Review" target="new">Sales Performance Review</a>
<br>
<a href="https://github.com/CameronCSS/Data-Analysis/tree/main/SLC%20civilian%20complaints" target="new">SLC civilian complaints</a>
  <br>
  <br>
</details>

## Analysis Experience
:ballot_box_with_check: Power BI / Tableau Visual Reports
<br> :ballot_box_with_check: Case study and data breakdowns
<br> :ballot_box_with_check: API pulls and database building
<br> :ballot_box_with_check: Full analysis and reports on data
<br> :ballot_box_with_check: Buidling finished Dashboards
    
### Data Visualization sample
----
### [ Project Description ]
  :small_blue_diamond: This dashboard was built with Tableau public using public Netflix date up to 2020.
    <br>
    <br>
    
![Netflix](https://user-images.githubusercontent.com/121735588/215313601-be1ab656-af52-49a0-86a4-2b1a42910aec.png)
<br>

_Full project_ :arrow_right: <a href="https://cameroncss.github.io/Data-Analysis/Netflix/index.html" target="new">_Netflix Movies and TV Shows_</a>
   <br>
        <sub>_*Click link for full interactive dashboard_</sub>
    <br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>
    
----
 <a name="Programming"></a>  
# Programming languages / Code
 
<details>
<summary>View Projects</summary>
<a href="https://github.com/CameronCSS/Programming-Languages/tree/main/Python%20Wage%20Calculator" target="new">Python Wage Calculator</a>
</details>

## Programming Experience
:ballot_box_with_check: Google data analytics professional certificate (*R) 
<br> :ballot_box_with_check: Completed Kaggle 'Intro to Programming' Course
<br> :ballot_box_with_check: Built out a few simple programs in Python through Self Learning
<br> :ballot_box_with_check: C# app building in High School
    
### Python code sample
----
### [ Project Description ]

:small_blue_diamond: A Simple Python code that Creates a UI and then calculates your Wages/Bills

 <br>
[ Demonstration ] :arrow_heading_down:
 <br>
 <br>


![wage-calculator (3)](https://user-images.githubusercontent.com/121735588/211175350-f105e7f0-e049-4288-925c-4c9c8fa92d97.gif)
 
 
<br>
  [ Code snippet ] :arrow_heading_down:
<br>
<br>
    
```python
# create the add bill button
		self.add_bill_button = QPushButton('Add Bill')
		self.add_bill_button.clicked.connect(self.add_bill)
		self.bills_layout.addWidget(self.add_bill_button)
		
		# create the calculated income label
		self.calculated_income_label = QLabel('Calculated Income: 0.00')
		self.bills_layout.addWidget(self.calculated_income_label)
		
		# create the remaining balance label
		self.remaining_balance_label = QLabel('Remaining Balance: 0.00')
		self.bills_layout.addWidget(self.remaining_balance_label)
		
		# set the initial tab
		self.tabs.setCurrentIndex(0)
		
	def calculate_income(self):
		# calculate the income
		try:
			hourly_wage = float(self.hourly_wage_input.text())
			hours_worked = float(self.hours_worked_input.text())
			
			calculated_income = hourly_wage * hours_worked
			
			self.calculated_income_label.setText('Calculated Income: {:.2f}'.format(calculated_income))
			
			self.remaining_balance = calculated_income
			self.remaining_balance_label.setText('Remaining Balance: {:.2f}'.format(self.remaining_balance))
			
			self.tabs.setCurrentIndex(1)
		except:
			pass

```

<br>
_Full project_ :arrow_right: <a href="https://github.com/CameronCSS/Programming-Languages/tree/main/Python%20Wage%20Calculator" target="new">Python Wage Calculator</a>
    
<p align="right">(<a href="#readme-top">back to top</a>)</p>
    
  -------

<a name="Currently-working-on"></a>
## Currently working on

- 📊 Power BI Deep dive - I am currently building several reports in Power BI to showcase my personal understanding of what it can do
- 📝 I’m currently working on a report about <a href = "https://github.com/CameronCSS/Data-Analysis/tree/main/SLC%20Homless%20Data"> **SLC Homeless numbers </a> after shutting down Homeless Centers**
- :soon: Finishing up Week #2 of the <a href ="https://github.com/CameronCSS/SQL-Projects/tree/main/8%20Week%20SQL%20Challenge%20%23%201"> 8 Week SQL Challenge </a> with SQL query answer breakdowns.
- ⚡ Expanding my knowledge of Python and pandas library**
  
<a name="About"></a>  
## About Me

Strong problem solver, ability to identify and analyze complex issues, self motivated, endlessly looking to improve. My goal is to utilize my skills in SQL, Power BI, Tableau, and Python to turn complex data sets into easy to understand visuals that get everyone interested in the insights.

Currently seeking new opportunities. <li><a href="#Contact">Contact Me</a></li>

----

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://www.mysql.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" width="40" height="40"/> </a> <a href="https://www.postgresql.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="postgresql" width="40" height="40"/> </a> <a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> <a href="https://pandas.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/pandas/pandas-original.svg" alt="pandas" width="40" height="40"/> </a> <a href="https://www.photoshop.com/en" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg" alt="photoshop" width="40" height="40"/> </a> <a href="https://www.blender.org/" target="_blank" rel="noreferrer"> <img src="https://download.blender.org/branding/community/blender_community_badge_white.svg" alt="blender" width="40" height="40"/> </a> </p>

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=CameronCSS&layout=compact&theme=transparent&langs_count=6)](https://cameroncss.github.io/)
<br>
![Cameron's GitHub stats](https://github-readme-stats.vercel.app/api?username=CameronCSS&show_icons=true&theme=transparent&hide=issues,contribs)

<a name="Contact"></a> 
## Contact

<div style="display: flex;">
  <table style="flex: 1;">
  
||
| --- |
| :e-mail: :heavy_minus_sign: CameronSeamons@gmail.com |
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
