# 🔮 Mastering Web Event Analytics with SQL ## 
## Steps 🪜
- Sign up [Aiven](https://aiven.io) or login ,to create a new service and select MySql
- Launch Dbeaver
- Create a new MySql database connection.
- Insert/Write/Paste the credentials from the aiven account to the Dbeaver ie,Host,Port,Postgress,Username ,Password
- Test connection ✅

### 📊 Overview ✨
This repository contains a collection of **SQL queries** designed to analyze web event data effectively.
### Features 🔥
- ⏲️ Events by Time of Day (Morning, Evening, Peak Hours).
- 🔝 Top 5 most used channels
- 📈  web events happened per month in 2016
- 🌓  web events happened in the evening (after 6pm)
- 🎯  Channel Performance & User Engagement Metrics

### 📁  Example of SQL Queries used in analyzing web events data using SQL
### 1️⃣ **Total Web Events Count**
```sql
SELECT COUNT(*) FROM web_events;
```
### 2️⃣ **Which channels had more than 100 web events**
``` Sql
select channel,COUNT (*)as event_count
from web_events
group by channel
having count (*)> 100;
```
### 3️⃣**Web events that occurred on weekends**
``` sql
select COUNT(*) from web_events where extract (DOW from occurred_at) in (0,6);
```
### 4️⃣ **How many web events happened per month in 2016**
```sql
 select DATE_TRUNC ('month',occurred_at)as month,COUNT(*) as event_count
 from web_events 
 where occurred_at between '2016-01-01' AND '2016-12-31'
 group by month 
 order by month;
```

**Run SQL queries in your preferred SQL environment**
   - PostgreSQL, MySQL

🏆 Author
👤 **kelvin Kaira** 
## ⭐ Support
