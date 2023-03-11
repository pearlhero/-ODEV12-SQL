# -ODEV12-SQL
dvdrental sorgu senaryoları çözümleri
Sorgu 1- film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
Çözüm 1- SELECT COUNT(length) FROM film
WHERE length > 
( SELECT AVG(length) FROM film
);
<img width="527" alt="Ekran Resmi 2023-03-11 18 15 34" src="https://user-images.githubusercontent.com/116847744/224492466-18b4839a-ad74-48a3-99eb-831e8a2e9b88.png">

Sorgu 2- film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
Çözüm 2- SELECT COUNT(film) FROM film
WHERE rental_rate =
(SELECT MAX(rental_rate) FROM film
);
<img width="533" alt="Ekran Resmi 2023-03-11 18 22 06" src="https://user-images.githubusercontent.com/116847744/224492708-283efc64-d722-47e6-8495-50159b060eee.png">

Sorgu 3- film tablosunda en düşük rental_rate ve en düşük replacement_cost değerlerine sahip filmleri sıralayınız.
Çözüm 3- SELECT title FROM film
WHERE rental_rate = (SELECT MIN(rental_rate) FROM film) 
AND replacement_cost = (SELECT MIN(replacement_cost) FROM film);
<img width="607" alt="Ekran Resmi 2023-03-11 18 30 12" src="https://user-images.githubusercontent.com/116847744/224493124-2f0d8709-296b-4a6d-94e5-f8d3e2a3adf3.png">

Sorgu 4- payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.
Çözüm 4- SELECT COUNT(payment_id), customer_id FROM payment 
GROUP BY customer_id
ORDER BY COUNT DESC;
<img width="570" alt="Ekran Resmi 2023-03-11 18 45 33" src="https://user-images.githubusercontent.com/116847744/224493943-b6415306-46e9-443b-bacb-89e7d410262e.png">
