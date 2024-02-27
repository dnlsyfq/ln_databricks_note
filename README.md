# HTML
```
displayHTML("""
  <font size="6" color="red" face="sans-serif">Title</font>
""")
```


# Create Table from CSV in SQL

```
DROP TABLE IF EXISTS <name>;

CREATE TABLE <name>
  USING csv
  OPTIONS (PATH "/databricks-datasets/Rdatasets/data-001/csv/ggplot2/diamonds.csv", header "true")
```

# Create Table from CSV in Spark
```
df = spark.read.csv("/databricks-datasets/Rdatasets/data-001/csv/ggplot2/diamonds.csv", header="true",inferSchema="true")
```

```
df = spark.read.format('csv').option('inferSchema','true').option('header','true').load('dbfs:/databricks-datasets/bikeSharing/data-001/day.csv')
df.registerTempTable('bikeshare')
```

# Spark SQL
```
display(
  spark.sql(" SELECT ...")
)
```

# Spark Python ETL

```
from pyspark.sql.functions import avg

display(df.select('col1','col2').groupBy('col1').agg(avg('col2')))
```
