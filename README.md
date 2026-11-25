# Question 3: Library Returns and Overdue Fines

PostgreSQL. Run `solution.sql` from top to bottom. It creates its own schema `q3`.
Scheduled jobs use pg_cron.

## Index
`loans(book_id) WHERE returned_on IS NULL`

A partial index that only contains unreturned loans. The search asks for one book's open loans, so the index stays small as returned history grows and is exactly what the query needs.

Assumption: in pr_refresh_overdue, a loan counts as overdue if it is unreturned as of the given date and due before it.
