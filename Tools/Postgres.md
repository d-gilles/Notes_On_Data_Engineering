<img src="https://cdn-icons-png.flaticon.com/512/5968/5968342.png" width="100" height="100" alt="Postgres">

# Postgres

### ⁉️ Overview

PostgreSQL, also known as Postgres, is a powerful open-source relational database management system. It uses and extends the SQL language to provide a robust set of features and capabilities, such as data integrity, concurrency control, and automated data processing. Postgres is highly scalable and can handle large amounts of data, making it a popular choice for many organizations. It is commonly used for web applications, data warehousing, and GIS applications, among others. Postgres also has a strong community of developers, allowing for easy integration with many other tools and technologies.

### **🧑‍🎓** Resources
<details><summary>Here are some learning resources for Postgres:</summary>

Here are some open source and free resources available to learn PostgreSQL:

1. **Official PostgreSQL Documentation:** This is the official documentation for PostgreSQL, which includes everything you need to know about PostgreSQL, from installation to advanced topics. It's available online for free and is regularly updated. You can access it here: https://www.postgresql.org/docs/

2. **PostgreSQL Tutorial:** This is a comprehensive tutorial that covers all the basic concepts of PostgreSQL. It includes hands-on exercises and practical examples. You can access it here: https://www.postgresqltutorial.com/

3. **PostgreSQL for Beginners:** This is a free Udemy course that covers all the basics of PostgreSQL. It's a great resource for beginners who want to learn PostgreSQL from scratch. You can access it here: https://www.udemy.com/course/postgresql-for-beginners/

4. **PostgreSQL Exercises:** This is a collection of exercises and solutions to help you practice and improve your PostgreSQL skills. It covers everything from basic queries to advanced topics like stored procedures and triggers. You can access it here: https://pgexercises.com/

5. **PostgreSQL Community:** This is a community of PostgreSQL users and developers who share their knowledge and experiences. You can ask questions, share your knowledge, and connect with other PostgreSQL users. You can access it here: https://www.postgresql.org/community/

6. **PostgreSQL Wiki:** This is a community-driven wiki that contains a wealth of information about PostgreSQL. It covers everything from basic concepts to advanced topics, and includes tutorials, examples, and best practices. You can access it here: https://wiki.postgresql.org/wiki/Main_Page

7. **PostgreSQL YouTube Channels:** There are several YouTube channels dedicated to PostgreSQL that provide tutorials, live sessions, and explanations on various topics related to PostgreSQL. Some of the popular channels are:
    - [Learn PostgreSQL Tutorial - Full Course for Beginners](https://www.youtube.com/watch?v=qw--VYLpxG4)
    - [PostgreSQL tutorial for beginners 2021: setup postgreSQL and pgAdmin](https://www.youtube.com/watch?v=DMl5fsc8PSk)
    - [PostgreSQL Tutorial For Beginners | Learn PostgreSQL](https://www.youtube.com/watch?v=-VO7YjQeG6Y)

I hope these resources help you learn PostgreSQL!

</details>

### 💻 Commands
<details><summary>Access Postgres via `pgcli` from Terminal:</summary>


`pgcli -h [localhost](http://localhost) -p 5432 -u root -d ny_taxi`  h=Host, p=Port, u=user, d=database name

| \! [command]  | Pass commands to shell. |
| --- | --- |
| \#  | Refresh auto-completions.  |
|  \? | Show Commands. |
| \T [format]      | Change the table format used to output results |
|  \c[onnect] database_name | Change to a new database.    |
| \conninfo    | Get connection details    |
| \copy [tablename] to/from [filename]  | Copy data between a file and a table. |
| \d[+] [pattern] | List or describe tables, views and sequences.  |
| \dD[+] [pattern]  | List or describe domains.     |
| \dE[+] [pattern] | List foreign tables.                           |
| \dF[+] [pattern]  | List text search configurations. |
|  \dT[S+] [pattern] | List data types  |
| \db[+] [pattern] | List tablespaces.  |
| \ddp [pattern] | Lists default access privilege settings. |
| \df[+] [pattern] | List functions. |
| \di[+] [pattern] | List indexes.       |
| \dm[+] [pattern] | List materialized views.     |
|  \dn[+] [pattern] | List schemas.  |
|  \dp [pattern] | List roles.  |
|  \ds[+] [pattern] | List sequences.        |
|  \dt[+] [pattern] | List tables.      |
| \du[+] [pattern] | List roles.   |
|  \dv[+] [pattern] | List views.          |
| \dx[+] [pattern] | List extensions. |
| \e [file] | Edit the query with external editor. |
| \h | Show SQL syntax and help.  |
| \i filename | Execute commands from file.       |
| \l[+] [pattern] | List databases.    |
| \n[+] [name] [param1 param2 ...] | List or execute named queries. |
|  \nd [name] | Delete a named query. |
|  \np name_pattern | Print a named query.    |
| \ns name query | Save a named query.  |
| \o [filename] | Send all query results to file. |
|  \pager [command] | Set PAGER. Print the query results via PAGER. |
| \pset [key] [value] | A limited version of traditional \pset |
| \q | Quit pgcli. |
| \refresh | Refresh auto-completions. |
| \sf[+] FUNCNAME | Show a function's definition. |
| \timing | Toggle timing of commands. |
| \watch [sec=2] | Execute query every sec seconds. |
| \x | Toggle expanded output.  |
| quit  | Quit pgcli. |

</details>

### 📦 Running Postgres in Docker

To run a postgres database in a Docker container, you can use the following command in your terminal:

```
docker run -it \\
-e POSTGRES_USER="root" \\
-e POSTGRES_PASSWORD="root" \\
-e POSTGRES_DB="ny_taxi" \\
-v $(pwd)/ny_taxi_postgres_data:/var/lib/postgresql/data \\
-p 5432:5432 \\
postgres:13

```

This will start a session in Docker with Postgres running. You can connect to it using `pgcli` with the following command:

```
pgcli -h localhost -p 5432 -u root -d ny_taxi

```

From there, you can use various commands to interact with the Postgres database. For example, `\\dt` will show the data tables, and `\\d ny_taxi` will show the data from the `ny_taxi` table.
</br>
A more convenient way to access the postgres db is using pgAdmin.
