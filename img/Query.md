## 1 
- SELECT * FROM `events` WHERE `price` IS NULL;
## 2
- SELECT * FROM `locations` ORDER BY `name` ASC;
## 3 
- SELECT * FROM `events`WHERE `price` < 20 AND `duration` < '03:00:00';
## 4 
- SELECT * FROM `events` WHERE `start` >= '2023-12-01' AND `end_of_sale` < '2024-01-01';
## 5
-  SELECT * FROM `events` WHERE `duration ` > '02:00:00';
## 5 
- SELECT events.*, events.name AS `nome`, events.start AS `data di inizio`, TIME(events.start) AS `ora di inizio`, TIME(events.end_of_sale) AS `ora di fine`, events.duration AS `durata totale` FROM `events`;
## 6 
- SELECT * FROM `events` WHERE `user_id`= 1202;
## 7 
- 
## 8 
- SELECT * FROM `users` WHERE `role_id`= 1 OR `role_id`= 2;
## 9 
- SELECT * FROM `event_tag` WHERE `tag_id`= 1;
## 10 
- SELECT `tags`.`name`, AVG(events.price) AS aprezzo_medio FROM `tags` INNER JOIN `event_tag` ON `tags`.`id` = `event_tag`.`tag_id` INNER JOIN events ON `event_tag`.`event_id` = `events`.`id` GROUP BY `tags`.`name`;
## 11 
- SELECT `locations`.`name`, COUNT(`events`.`id`) AS numero_eventi FROM `locations` INNER JOIN events ON `locations`.`id` = `events`.`location_id` GROUP BY `locations`.`id`;
## 12
- SELECT `users`.* FROM `users` INNER JOIN `bookings` ON `users`.`id` = `bookings`.`user_id` WHERE `bookings`.`event_id` = 34;
## 13 
- SELECT CONCAT(`users`.`first_name`,' ', `users`.`last_name`) AS nome_cognome FROM `users` INNER JOIN `bookings` ON `users`.`id`= `bookings`.`user_id` WHERE `bookings`.`event_id`= 2;
## 14 
- SELECT`events`.`id`, `events`.`name`,`events`.`start`,`events`.`total_tickets`,COUNT(`bookings`.`id`) AS totale_prenotazioni FROM `events` INNER JOIN `bookings` ON `eventS`.`id`= `bookings`.`event_id` GROUP BY `events`.`id`, `events`.`name`,`events`.`start`,`events`.`total_tickets` HAVING COUNT(`bookings`.`id`) = `events`.`total_tickets`;
## 15 
-   SELECT COUNT(`events`.`location_id`) AS LOCATION_COUNT, `location_id`
FROM `events`
INNER JOIN `locations`
ON `events`.`location_id` = `location_id`
GROUP BY `events`.`location_id`
ORDER BY LOCATION_COUNT ASC;
## 16 
- SELECT `users`.`first_name`, COUNT(`bookings`.`event_id`) AS numero_eventi
FROM `users`
INNER JOIN `bookings` ON `users`.`id` = `bookings`.`user_id`
GROUP BY `users`.`id`, `users`.`first_name`
HAVING COUNT(`bookings`.`event_id`) > 70;
## 17 
-SELECT `events`.`name` AS event_name, `locations`.`name` AS location_name, COUNT(`bookings`.`event_id`) AS numero_prenotazioni, (`events`.`total_tickets` - COUNT(`bookings`.`event_id`)) A biglietti_disponibili
FROM `events`
INNER JOIN `locations` ON `events`.`location_id` = `locations.id`
LEFT JOIN `bookings` ON `events`.`id` = `bookings`.`event_id`
GROUP BY `events.id`, `events`.`name`, `locations`.`name`, `events`.`total_tickets`;

