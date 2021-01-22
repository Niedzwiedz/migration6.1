# README

App showing migration time differences between rails 6.0 and 6.1 when running db:migrate (even when
no new migrations are present)
rails 6.0 version

* Ruby version
2.7.2

* Configuration
`docker-compose build`
`docker-compose up`

* Database creation
`docker container exec -it <container> rails db:create`

* Database initialization
`docker container exec -it <container> rails db:migrate db:seed`

* Running db:migrate without new migrations:
(To reproduce: run db:migrate again)
`time docker container exec -it <container> db:migrate`

Seed data contains n(currently  4000) number of new tenants/schemas with json inside each of tenats input tables


```
2000 schemas
_______________________________________________________

Executed in  199.69 secs   fish           external
  usr time  238.01 millis   91.00 micros  237.92 millis
  sys time  250.77 millis  429.00 micros  250.34 millis

4000 schemas
________________________________________________________
Executed in  663.30 secs   fish           external
   usr time  400.41 millis  164.00 micros  400.25 millis
   sys time  374.97 millis  986.00 micros  373.99 millis
```
