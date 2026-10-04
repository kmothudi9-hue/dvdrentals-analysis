SELECT f.title, COUNT(r.rental_id) AS rental_count
FROM rental r
JOIN inventory i ON r.inventory_id = i.inventory_id
JOIN film f ON i.film_id = f.film_id
GROUP BY f.title
ORDER BY rental_count DESC
LIMIT 10;


### 🎬 Power BI Dashboard - Top 10 Rented Films
- Connected PostgreSQL dvd_rental to Power BI via Npgsql
- Built relationships: rental *->1 inventory *->1 film
- Visual: Bar chart with Count of rental_id, Top N filter, axis titles
- Insight: Bucket Brotherhood is #1 with 35 rentals, top films cluster at 31-35 rentals
