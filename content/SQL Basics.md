---
publish: true
title: SQL Basics
created: 2026-05-19T13:55:12.067+05:30
modified: 2026-05-19T13:55:12.067+05:30
---

> [!todo] Complete SQL murder

**Links**

- https://mystery.knightlab.com/walkthrough.html
- https://github.com/NUKnightLab/sql-mysteries#sql-murder-mystery

What is SQL?
SQL stands for structure query language. It's the instructions that are used to reterive data from relational database.
The collection of these instruction makes up the query language.

What is a relational database?
A database is a collection of data. It's a place where all the data about particular thing is dumped. These data are grouped under tables.
A relational databases are databases where there is a relation between two tables.

ERD - Entity Relationship Diagram
Diagram used to represent the relationship database.

SQL commands are **not case sensitive**. It's a convention to follow UPPERCASE for sql keywords so it's easier to read from other words in the query.

Query examples

```sql
SELECT *
FROM <table>;
```

`*` let's us select all the columns from the table.
If we want to select specific tables we enter the column names separated by comma `,`

```sql
SELECT column_1, column_2
FROM <table_name>;
```

```sql
SELECT *
FROM <table_name>
LIMIT <number>;
```

To check possible values of the column use `DISTINCT`

```SQL
SELECT DISTINCT <column_name> FROM <table_name>;
```

Queries are ended with `;`

The `WHERE` clause of the query is used to filter out the results from the table

```sql
SELECT * 
FROM <table_name> 
WHERE <filter_value>
```

Example:

```sql
SELECT * FROM person WHERE name = 'Davina Gangwerp'
```

`AND` keyword and `OR` keyword's can also be used in the where clause to fine grain the result much further

Example:

```sql
SELECT * FROM crime_scene_report 
WHERE type = 'theft' 
AND city = 'Chicago';
```

Wild cards
`%` and `_`

`%` matches anything in-between,
Example: `Ca%a` can match `Canada` and `California`.

`_` tells to match exactly one character at place where it is.
Example: `'B_b'` would match `'Bob'` and `'Bub'` but not `'Babe'` or `'Bb'`.

> [!info] When using wildcards, you don't use the `=` symbol; instead, you use `LIKE`.

Use `>` and `<`  for grater than and lesser than calculation.
`BETWEEN` & `AND` can also be used. This work with the alphabets as well

> [!info] SQL commands are not case-sensitive, but `WHERE` query values for `=` and `LIKE` are

---

SQL Aggregator function

`MAX`
`MIN`
`SUM`
`AVG`
`COUNT`
`ASC` & `DESC` for ascending and descending ordering
`ORDER BY`

---

> \[!success ] Murder was `Jeremy Bowers` who was hired by `Miranda Priestly`

---
