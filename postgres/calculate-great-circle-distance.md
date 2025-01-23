# Calculate the great circle distance between two cities

## Activate extensions
```sql
CREATE EXTENSION cube;
CREATE EXTENSION earthdistance;
```

## Example query

```sql
WITH
place1 AS (
    SELECT place_name as name, latitude, longitude
    FROM cities
    WHERE place_name = 'Sonthofen'
)
SELECT
    id,
    postal_code,
    place_name,
    round(earth_distance(
        ll_to_earth(cities.latitude, cities.longitude),
        ll_to_earth(place1.latitude, place1.longitude)
    ) / 1000) as distanz_zur_huimat,
    cities.latitude,
    cities.longitude
FROM place1, cities
WHERE admin_name_3 ilike '%allgäu%';
```

