# SimpleLuigiDataPipeline

##Problem
Tim Sales  Punya Data yang disimpan di docker image
Tim Product mempunya data yang disimpan di file csv
Tim Data Science membutuhkan data scraping dari website untuk melihat pola judul iklan yang dituliskan dalam website OLX

##Data Engineer Solution
Diperlukan Data Warehouse untuk mengumpulkan ketiga data tersebut sehingga mudah diakses seluruh tim

![](pic/untitled.png)


###Membuat ETL Pipeline Design:

Extract:
- Extract from CSV
- Extract from PosgreSQL di Docker Image
- Scrape data HTML

Transform:
- Parse data HTML
- Transform data dari hasil scraping: Ubah format tanggal, split kelurahan dan kota kabupaten, enrich url_listing
- Transform data sales: extract angka dari discount_price dan actual_price
- Transform data product: delete several unnecessary column, select only validated row


Load:

Save the output totables on Postgres
Tools: Python, Pandas, Luigi, dan PostgreSQL
Output lainnya: Json file



Other process:

Datawarehouse yang telah dibuat dijadikan image lalu diupload ke dockerhub
