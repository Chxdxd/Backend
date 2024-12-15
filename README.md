<<<<<<< HEAD
## Setup


Creating virtual Environments
```bash
python -m venv /path/to/new/virtual/environment
```

To activate our venv in Windows
```bash
.\venv\Scripts\activate
```

we need to install flask in our terminal
```bash
pip install Flask
```



## Containers

To create and execute our container we can apply the command
```bash
docker run --name postgres -e POSTGRES_USER=chpalma -e POSTGRES_PASSWORD=chpalma -e POSTGRES_DB=chpalma_db -itd postgres:17.2-alpine3.21
```
For this example we choose 17.2- because its small size.



To execute a command within a container
```bash
docker exec -it postgres [command]
docker exec -it postgres shell
```

```bash
docker exec -it postgres psql -U chpalma
```


To access to postgres within our container
```bash
docker exec -it postgres psql -U chpalma
```

To create a database within our container
```bash
chpalma=# CREATE DATABASE devnet;
```

To connect to our database:
```bash
chpalma=# \c devnet
```


To create a table in our database
```bash
chpalma=# CREATE TABLE cats (
    id SERIAL PRIMARY KEY,
    name varchar(40),
    grade int,
    years real,
    avg_csat real
)
```

To insert values in our table:
```bash
INSERT INTO cats (name, grade, years,avg_csat) VALUES ('bryant', 10, 5.4, 10.0); 
```

To consult data from our table:
```bash
select * from cats;
id |  name  | grade | years | avg_csat
----+--------+-------+-------+----------
  1 | bryant |    10 |   5.4 |       10
  2 | Seb    |     6 |   1.4 |      5.8
```

The character * is to consult all the elements from the table
We can consult specific information based on the parameters of our request.
```bash
select * from cats where id = 1;

 id |  name  | grade | years | avg_csat
----+--------+-------+-------+----------
  1 | bryant |    10 |   5.4 |       10
```

```bash
devnet=# select * from cats where id > 1;
;
 id | name | grade | years | avg_csat
----+------+-------+-------+----------
  2 | Seb  |     6 |   1.4 |      5.8
(1 row)
```

=======
# Backend
>>>>>>> 1682be935b438c1fe354573e0bba1d60433f3d23
