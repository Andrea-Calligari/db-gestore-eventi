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
