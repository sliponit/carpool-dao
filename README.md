# carpool-app


# API routes
```
GET /auth/rides?origin=lat,lng&destination=lat,lng&radius= 
POST /auth/rides { origin: lat,lng, destination: lat,lng, time: timestamp, price }
POST /auth/rides/:id/book 
GET /rides
```

```
docker run --name some-postgis -e POSTGRES_PASSWORD=example -p 5432:5432 postgis/postgis:14-3.2-alpine
```


```sql
CREATE TABLE rides (
  rides_id SERIAL PRIMARY KEY,
  origin geography(point) not NULL,
  destination geography(point) not NULL,
  price decimal not NULL,
  driver VARCHAR(42) not NULL,
  passenger VARCHAR(42),
  time TIMESTAMP not null,
  created_at TIMESTAMP default NOW()
)

INSERT INTO rides (origin, destination, price, driver, passenger, time)
  VALUES ('POINT(2.5559 49.0083)', 'POINT(2.5559 49.0083)', 1.5, 'allo', 'ola', NOW());

select * from rides 
```