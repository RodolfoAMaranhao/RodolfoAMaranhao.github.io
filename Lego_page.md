## Analyzing a Lego Database: Building an ERD with Lucidchart and Utilizing SQL Joins

**Project description:** The main objective of this project is to work with a large Lego database by first creating a diagram to visualize the relationship between primary and foreign keys in the database. Then, we can utilize SQL to perform joins and analyze the database.

<img src="images/Lego ERD.png"/>

After creating a diagram in LucidChart it becomes easier to imagine how we can perform joins and pull information from multiple tables. For example, we can join the Themes table with the Sets table to find out what were the names of the themes and the count of such themes per year.

```sql
-- What were the names and counts of parent themes per recent year?

SELECT s.name AS Set_name, t.name AS Parent_theme_name, s.year, COUNT(*) AS Count_Theme_Name
FROM themes AS t
JOIN sets AS s
ON t.id = s.theme_id
GROUP BY t.parent_id
ORDER BY s.year
DESC
;
```

Additionally we can perform multiple joins to visualize the database. keeping in mind this is not the most runtime efficient way, it is just an example.

```sql
-- We can also make multiple joins to see the database in a comprehensive manner

SELECT *
FROM sets AS s
JOIN inventories AS i ON s.set_num = i.set_num
JOIN inventory_parts as ip ON i.id = ip.inventory_id
JOIN parts AS p ON ip.part_num = p.part_num
JOIN part_categories AS pc ON p.part_cat_id = pc.id
LIMIT 10
;

```

Normally, we would want to look at specific information and not just every single column, we could create filters to visualize specific information across multiple tables.

```sql
-- If we want to find a specific set name's part and part category we can apply filters

SELECT s.name AS Set_name, p.name AS Part_name, pc.name AS Part_category_name
FROM sets AS s
JOIN inventories AS i ON s.set_num = i.set_num
JOIN inventory_parts as ip ON i.id = ip.inventory_id
JOIN parts AS p ON ip.part_num = p.part_num
JOIN part_categories AS pc ON p.part_cat_id = pc.id
WHERE s.name = "Weetabix Castle"
;

```


For more details see <a href="https://github.com/RodolfoAMaranhao/Lego_parts_analysis_SQL_ERD">Project Files</a> 


