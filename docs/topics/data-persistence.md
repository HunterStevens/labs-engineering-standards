# Data Persistence

## (DP-100) Managed Services Only

Only fully managed storage services are to be used for hosting a database in a
shared environment.

Rationale:

- Managing database servers is an incredibly complex and resource intensive
  endeavor. By utilizing management services, that operational overhead are
  greatly reduced.

Exceptions:

- None

## (DP-200) Approved Database Engines

Only the following database engines are approved for project in Labs:

Engine       | Permitted Versions | Providers
------------ | ------------------ | ------------
Postgres     | > 11.5.0           | AWS RDS
             |                    | Heroku Postgres

All other database engines are prohibited, including:

- MongoDB, SQLite, MySQL, DB2

Rationale:

- We restrict the database engine use in Lambda Labs so that we can focus our
  resources on a subset of available technologies. By narrowing the field of
  choices, we feel that product quality will be improved through the sharing of
  common knowledge and reusable components.

Exceptions:

- None
