# Chapter 3: Basics of Option Market Making Data Analysis using PySpark

Welcome back to our series on How to use PySpark for Option Market Making Data Analysis! In the previous chapter, we learned about setting up a PySpark environment for option market making applications. Now, we'll dive into the basics of option market making data analysis using PySpark.

To help us navigate through this chapter, we have a special guest joining us: Wes McKinney, the creator of Pandas, an open-source data analysis and manipulation library for Python. As PySpark is a distributed computing framework, we'll discuss the differences between traditional Pandas data analysis and distributed data analysis in PySpark with Wes.

We'll begin by exploring the basic concepts of options and market making. Then, we'll delve into how to perform option market data analysis using PySpark. We'll examine various PySpark functions, such as `filter`, `groupBy`, and `agg`, and how to use them in the context of option market making data sets. Additionally, we'll look at some more advanced PySpark functions like `window`, `rolling`, and `udf`.

By the end of this chapter, you will have a good understanding of the fundamentals of option market making data analysis using PySpark, and how to utilize PySpark functions to dissect and analyze option market data sets. So, let's get started with our special guest, Wes McKinney, and learn about how to make Pandas work with PySpark for options market data analysis.
# Chapter 3: Basics of Option Market Making Data Analysis using PySpark

Welcome back to our series on How to use PySpark for Option Market Making Data Analysis! In the previous chapter, we learned about setting up a PySpark environment for option market making applications. Now, we'll dive into the basics of option market making data analysis using PySpark.

To help us navigate through this chapter, we have a special guest joining us: Wes McKinney, the creator of Pandas, an open-source data analysis and manipulation library for Python. As PySpark is a distributed computing framework, we'll discuss the differences between traditional Pandas data analysis and distributed data analysis in PySpark with Wes.

We'll begin by exploring the basic concepts of options and market making. Then, we'll delve into how to perform option market data analysis using PySpark. We'll examine various PySpark functions, such as `filter`, `groupBy`, and `agg`, and how to use them in the context of option market making data sets. Additionally, we'll look at some more advanced PySpark functions like `window`, `rolling`, and `udf`.

By the end of this chapter, you will have a good understanding of the fundamentals of option market making data analysis using PySpark, and how to utilize PySpark functions to dissect and analyze option market data sets. So, let's get started with our special guest, Wes McKinney, and learn about how to make Pandas work with PySpark for options market data analysis.
In this chapter, we will explore some basic concepts of option market making data analysis using PySpark. We'll examine various PySpark DataFrame functions, such as `filter`, `groupBy`, and `agg`, and how to utilize them in the context of option market making data sets.

For example, let's say we have a DataFrame `optionData` that contains option market making data with columns "symbol", "strike", "expiration", "bid", "ask", and "volume". We want to filter this DataFrame to only include options with a strike price greater than or equal to $50 and an expiration date later than Jan 1, 2022.

We can use the `filter` function to accomplish this as follows:

```python
from pyspark.sql.functions import col

optionDataFiltered = optionData.filter((col("strike") >= 50) & (col("expiration") > "2022-01-01"))
```

Next, we may want to group this filtered DataFrame by symbol and calculate the average bid, ask, and volume for each symbol. We can use the `groupBy` and `agg` functions to do this as follows:

```python
from pyspark.sql.functions import avg

optionDataGrouped = optionDataFiltered.groupBy("symbol").agg(avg("bid"), avg("ask"), avg("volume"))
```

Finally, we may want to sort this grouped DataFrame in descending order by ask price. We can use the `orderBy` function to do this as follows:

```python
optionDataSorted = optionDataGrouped.orderBy("ask", ascending=False)
```

These are just a few examples of the PySpark DataFrame functions we can use to perform option market making data analysis. With these functions in hand, we can easily perform complex queries and calculations on large data sets.


[Next Chapter](04_Chapter04.md)