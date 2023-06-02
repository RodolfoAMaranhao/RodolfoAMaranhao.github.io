## Revealing Patterns in High Schoolers' Behavior: EDA and ML for Predicting and Preventing Riding with Drinking Drivers

**Project description:** 





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

In this example we can look at the Name os the Lego set, the names of the parts and the names of the parts categories for only the set called "Weetabix Castle".


For more details see <a href="https://github.com/RodolfoAMaranhao/Lego_parts_analysis_SQL_ERD">Project Files</a> 
