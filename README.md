# 📌 End-to-End Supply Chain Analytics Workflow with N8N, Supabase, and Postgres

## Overview:
- The core reason for creating this project is to automate the workflow using the N8N tool.
- AtliQ Mart is an organic food manufacturer that specializes in only a few products but has disrupted the market in the two cities where they operate.
- Even though they handle very few products, their supply chain is immature.

- They face a classic supply chain issue, as they are unable to maintain optimal inventory levels.

- To address this, I created reports with the help of AI tools and used N8N automation to migrate the data directly from emails.


---

## ⚙️ Workflow Overview

### 1. 📧 Gmail Trigger  
- The workflow starts with the **Gmail Trigger node**. When ever we received a emails labeled in inbox it will be triggred, it also be triggred via different menans.
- It automatically monitors incoming files for supply chain data reports.
- Two files are monitored in this workflow India and USA.

### 2. 📂 Extract from File (CSV Parsing)  
- The **Extract From File** parse and aggregate the India and USA data.  
- Data is cleaned and structured before moving to the database.  

### 3. 🐘 Insert Data into Postgres  
- Parsed data is inserted into **Postgres tables** using the **Postgres Insert node**.  
- Two reports were inserted into database **India Daily Sales** and **USA Daily Sales**
- Each of them as an aggregate and order_line. 

### 4. ☁️ Cloud Hosting with Supabase  
- The Postgres database is hosted on **Supabase** (a cloud-native platform).
- Superbase is a way to host my postgres database on colud
- This ensures scalability, easy integration, and global accessibility.  

### 5. 📊 Data Analysis with Quadratic  
- The ingested data is analyzed using **Quadratic**, an AI-powered spreadsheet.  
- Instead of SQL queries, prompts like:  
  > *“Show me the top suppliers with delayed shipments”*  
  instantly generate insights.
- We can also view the trends and patterns using charts just like typing prompts.  

---
## Supply Chain Domain Knowledge:
I have gained basic fundamentals like: 

1. What is Orders and total lines in orders.
  - when ever we placed a order it willl get a order ID.
  - Total lines: In each of this we might place multiple orders with having same **orderID** in the same date we placed. This will creates order_lines.

2. Line_fill_rate (check if the placed order is delivered or not)
  -  We have to find a Ratio of total lines you've **delivered divided by total lines ordered**.

>  *For example: If we delivered 2 orders fully but yet 1 item is not delivered, so it's not considered full_delivery*.
> *"This is just to give an idea!"*
- It's 2/3 so that we will get the percentage. This will help us to see if the ordered items were delivered fully or not.
 
3. Volume fill_rate:
- This volume fill rate is the ratio of quantity delivered to the quantity ordered.
  > *For Example: The quantity ordered is 20 but the quantity delivered is 17*. So we divided by 17/20 we get 85% for this CustomerId.

4. IN Full Orders:
   - It counts how many orders we fulfilled.
   - In Full orders it was calculated at order level, not at the line level.
```
For Example:
If the customer has placed 20 items but they delivered 17 it was not full, even if they failed to deliver 1 item it was not considered IN FULL orders.
```
---
## Business Insights Using Quadratic:

### KIPs
- This KIPs is more important to the warehouses, managers, ect.

<img width="523" height="295" alt="image" src="https://github.com/user-attachments/assets/678b7fbd-d681-4652-af9e-562b7ab363bc" />


## 1. To track monthly on-time performance.

<img width="1288" height="731" alt="image" src="https://github.com/user-attachments/assets/7470b8a9-a6f0-4158-97c2-cf2ee0d7651d" />


## **If we want to look at the trends and patterns we can use charts**


<img width="990" height="531" alt="image" src="https://github.com/user-attachments/assets/88c33583-60bf-48ab-b83c-d0e1c59f309a" />

---

## 2. Show me the top 5 cutomers based on order_value OTIF%, IF%, and OT%, Also add the customer name, customer ID, and city in the table.

<img width="1051" height="215" alt="image" src="https://github.com/user-attachments/assets/beb627f3-bfb5-4bad-89dc-53d592b96c24" />

---

## End of the project:
With the help of AI tools and the N8N automation tool, we were able to save a lot of time in the workplace. In this project, I learned how to apply AI tools in the supply chain domain to create reports.

---
Overall, this project not only strengthened my technical skills but also gave me a practical understanding of how AI can transform supply chain analytics.


---

## Key Learnings

- Designed a fully automated **ETL pipeline** using N8N  
- Hands-on experience with **Postgres on the cloud (Supabase)**  
- Leveraged **AI tools for analytics** without writing complex SQL  
- Derived **real-world supply chain insights** from raw data.
