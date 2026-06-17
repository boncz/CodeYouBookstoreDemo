# Bookstore Database Demo

A classroom demo for Code:You Data Analysis students in Module 3. Starting from a single messy flat file, you'll design a relational database schema, build the database in Python, and write SQL queries to answer real business questions - then visualize the results with Matplotlib.

---

## Repository Structure

```
CodeYouBookstoreDemo/
│
├── data/
│   └── bookstore_flat.csv        # The raw flat file — your starting point
│
├── data/
│   └── bookstore_db_creation.ipynb   # Part 1: Design schema and build the database
    └── bookstore_analysis.ipynb      # Part 2: Write queries and create visualization
│
└── README.md
```

---

## Background

The flat file contains **5,200 rows** and **29 columns** representing sales transactions at a fictional independent bookstore chain. Every transaction includes information about the member who bought, the book they bought, the store where they bought it, and the details of the sale itself.

The problem: all of that information is crammed into one table. Member names repeat hundreds of times. Publisher addresses are duplicated on every book they've ever published. If a customer changed their email, you'd have to update it in potentially hundreds of rows.

Your job is to fix that.

---

## Part 1 — `bookstore_db_creation.ipynb`

**Goal:** Transform the flat file into a normalized relational database.

### What you'll do

1. Load the flat file into a Pandas DataFrame and inspect it
2. In the notes markdown cell, sketch out your proposed schema : what tables do you need? What are the primary and foreign keys?
3. Filter and reshape the DataFrame into separate tables matching your schema
4. Export each table as its own CSV
5. Create a SQLite database and load all tables into it

### Things to think about

- Which columns repeat the same information over and over? Those are candidates for their own table.
- What makes a good primary key? Can you use an existing column, or do you need to create one?
- What would break if a member changed their email address in the current flat file?

---

## Part 2 — `bookstore_analysis.ipynb`

**Goal:** Query the database you built and visualize what you find.

### Queries

| # | Question | Key Concepts |
|---|---|---|
| 1 | List every book sold in the Pacific region with its title, genre, and author | `JOIN`, `WHERE`, column aliasing |
| 2 | Which 5 genres generated the most total revenue? | `SUM`, `GROUP BY`, `ORDER BY`, `LIMIT` |
| 3 | Which members have spent more than $200 and made at least 3 transactions? | `HAVING` with multiple aggregate conditions |
| 4 | For each publisher, what is their single highest-revenue book? | Subquery or CTE, greatest-n-per-group pattern |

### Visualizations

Each query result should be turned into a chart using Matplotlib. Choose whatever chart type you think best represents the data and explain why you made that choice.

---

## Setup

### Requirements

- Python 3.8+
- Jupyter Notebook or JupyterLab
- pandas
- matplotlib
- sqlite3 *(part of Python's standard library — no install needed)*

### Getting started

Fork this repository to your own GitHub account, then clone your fork:

```bash
git clone <your-fork-url>
cd CodeYouBookstoreDemo
```

Open the project in VS Code:

```bash
code .
```

Open `bookstore_db_creation.ipynb` first, then `bookstore_analysis.ipynb`.

---

*Dataset synthesized by Claude (Anthropic) for use in this exercise.*
