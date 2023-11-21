# Week-5-Lux-academy-project
Using the dataset on :-https://www.kaggle.com/datasets/mbaabuharun/craigslist-vehicles copied the idea was to download the dataset, copy the data using SQL to a local MySQL or PostgreSQL database, move the data from local database to Snowflake, perform data transformation with DBT (data build tool), and use your preferred data visualization tool to create a report and dashboard.

 
#These are the steps that I followed to tackle the project described above:-
#Step 1:-
I first creeated database in posgress, pgAdmin :-
CREATE DATABASE craig_db
    WITH
    OWNER = postgres
    ENCODING = 'UTF8'
    LC_COLLATE = 'English_Kenya.1252'
    LC_CTYPE = 'English_Kenya.1252'
    LOCALE_PROVIDER = 'libc'
    TABLESPACE = pg_default
    CONNECTION LIMIT = -1
    IS_TEMPLATE = False;

   # Step 2:-
Then created table where the data would be stored :- 
CREATE TABLE IF NOT EXISTS public.craig_table
(
    "Unnamed: 0" character varying COLLATE pg_catalog."default",
    id character varying COLLATE pg_catalog."default",
    url character varying COLLATE pg_catalog."default",
    region character varying COLLATE pg_catalog."default",
    region_url character varying COLLATE pg_catalog."default",
    price character varying COLLATE pg_catalog."default",
    year character varying COLLATE pg_catalog."default",
    manufacturer character varying COLLATE pg_catalog."default",
    model character varying COLLATE pg_catalog."default",
    condition character varying COLLATE pg_catalog."default",
    cylinders character varying COLLATE pg_catalog."default",
    fuel character varying COLLATE pg_catalog."default",
    odometer character varying COLLATE pg_catalog."default",
    title_status character varying COLLATE pg_catalog."default",
    transmission character varying COLLATE pg_catalog."default",
    "VIN" character varying COLLATE pg_catalog."default",
    drive character varying COLLATE pg_catalog."default",
    size character varying COLLATE pg_catalog."default",
    type character varying COLLATE pg_catalog."default",
    paint_color character varying COLLATE pg_catalog."default",
    image_url character varying COLLATE pg_catalog."default",
    description character varying COLLATE pg_catalog."default",
    county character varying COLLATE pg_catalog."default",
    state character varying COLLATE pg_catalog."default",
    lat character varying COLLATE pg_catalog."default",
    "long" character varying COLLATE pg_catalog."default",
    posting_date character varying COLLATE pg_catalog."default",
    removal_date character varying COLLATE pg_catalog."default"
)
#Step 3:-
I then moved data from my local database to Snowflake using psql shell as the dataset was too large so I had copy it in parts:-
\COPY lux_table FROM 'C:/Users/Francis Mwangi/Desktop/SNAP/Lux/Part1.csv' WITH CSV ENCODING 'ISO-8859-1' HEADER DELIMITER ',';

#Step 4:-
In here, I was to move the data from postgress to Snowflake 
