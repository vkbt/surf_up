## Overview of the analysis:


We have been putting together a business plan to open Surf and Shake shop serving surfboards and ice cream to locals and tourists on the Hawaii island Oahu. We reached out to an investor W. Avy for backing and he asked us to analyze weather data about temperature trends for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round.

## Resources

Data Source: [hawaii.sqlite](https://github.com/vkbt/surf_up/blob/main/hawaii.sqlite)

Software and Packages: Anaconda **2022.05**, Python **3.7.13**, Conda **22.9.0**, Jupyter Notebook **6.4.12**, Pandas **1.3.5**, NumPy **1.21.6**, SQLAlchemy **1.4.39**

## Results:

For our analysis we received [hawaii.sqlite](https://github.com/vkbt/surf_up/blob/main/hawaii.sqlite) file containing weather data in Oahu from W.Avy.

Using **Conda** package management system we created a new virtual environment that runs the latest version of **Python 3.7** and contains all the **Anaconda** packages including **Jupyter Notebook** and named it PythonData. **Jupyter Notebook** is a powerful interactive computational environment that supports Python and is largely used for data analysis and visualization. We imported the data (a lightweight SQL database file with .sqlite extension) into Jupyter Notebook using SQLalchemy's [**create_engine()**](https://docs.sqlalchemy.org/en/20/core/engines.html#sqlalchemy.create_engine) function. [Structured Query Language (SQL)](https://en.wikipedia.org/wiki/SQL) is a standard language for storing, manipulating and retrieving data in databases, to write and execute queries. **SQLAlchemy** is an open-source SQL toolkit and object-relational mapper (ORM) for the Python. We used **Pandas**, a fast and powerful software library built on top of Python to manipulate and analyze the data and **NumPy**, a library for the Python, that supports large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays.

We used [**automap_base()**](https://docs.sqlalchemy.org/en/20/orm/extensions/automap.html#sqlalchemy.ext.automap.automap_base) function to map the tables and reflect sqlite database and established conversation with database through [**Session(engine)**](https://docs.sqlalchemy.org/en/14/orm/session_basics.html#session-basics) connection. [Session](https://docs.sqlalchemy.org/en/20/orm/session_basics.html) establishes all conversations with the database and represents a “holding zone” for all the objects which are loaded or associated with it during its lifespan.

For our analysis, we decided to compare temperature data for the months of June and December. We created two separate queries for June and December using [**session.query**](https://docs.sqlalchemy.org/en/14/orm/session_api.html#sqlalchemy.orm.Session.query) query, referenced Measurement table's temperatures and filtered June and December months. We converted results into two lists using Python [**list()**](https://docs.python.org/3/library/functions.html#func-list) and [**numpy.ravel**](https://numpy.org/doc/stable/reference/generated/numpy.ravel.html) functions. We used [**pandas.DataFrame**](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html) function to add lists into two data frame and applied
[**pandas.DataFrame.describe**](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.describe.html) function for descriptive statistics.

<img src="https://github.com/vkbt/surf_up/blob/main/Resources/1_june_describe.png" width=19.75% height=9.75%> <img src="https://github.com/vkbt/surf_up/blob/main/Resources/2_dec_describe.png" width=20% height=10%>

From the above images we can see that:
 - highest temperature in June is 85°F and in December is 83°F
 - average temperature in June is 75°F and in December is 71°F
 - lowest temperature in June is 64°F and in December is 56°F
 - standard deviation (a measure of how dispersed the temperature is in relation to the average temperature)for June is 3.26 and for December is 3.75

 ## Summary

For this project we collected and analyzed data using SQLalchemy, Pandas and NumPy libraries. We reflected sqlite database and tables, created a link from Python to reflected database. We created SQLalchemy queries, transferred them into Pandas data frames and performed a statistical analysis. 
We ran two additional queries for June and December referencing Measurement table's precipitation parameter, created data frames and ran a function for descriptive statistics.

<img src="https://github.com/vkbt/surf_up/blob/main/Resources/1_june_describe_prcp.png" width=19% height=9%> <img src="https://github.com/vkbt/surf_up/blob/main/Resources/2_dec_describe_prcp.png" width=20% height=10%>
