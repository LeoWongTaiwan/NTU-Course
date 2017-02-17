```
SET SQL_SAFE_UPDATES = 0;

SELECT count(*) FROM movie;

DELETE FROM movie 
WHERE ctrl_source_area_name <> "movie";

ALTER TABLE movie
  DROP COLUMN content_no,
  DROP COLUMN p_type,
  DROP COLUMN ctrl_source_name,
  DROP COLUMN content_type,
  DROP COLUMN main_id;
  
UPDATE movie SET pos_add_neg=(positive_score+negative_score);
UPDATE movie SET pos_less_neg=(positive_score-negative_score);

ALTER TABLE movie_2 ADD Movie_ID int;
UPDATE movie_2 SET Movie_ID = 1 WHERE title LIKE '%美國隊長3%' OR title LIKE '%英雄內戰%'  OR title LIKE '%美隊3%'OR title LIKE '%美隊 3%'OR title LIKE '%captain america%' OR title LIKE '%civil war%'OR title LIKE '%美國隊長 3%';
UPDATE movie_2 SET Movie_ID = 2 WHERE title LIKE '%死侍%' OR title LIKE '%惡棍英雄%'  OR title LIKE '%dead pool%'OR title LIKE '%deadpool%';
UPDATE movie_2 SET Movie_ID = 3 WHERE title LIKE '%屍速列車%' OR title LIKE '%屍速%';
UPDATE movie_2 SET Movie_ID = 4 WHERE title LIKE '%奇異博士%' OR title LIKE '%奇博%'OR title LIKE '%Dr. Strange%'OR title LIKE '%Dr.Strange%'OR title LIKE '%Doctor Strange%';
UPDATE movie_2 SET Movie_ID = 5 Where title LIKE '%動物方城市%' OR title LIKE '%方城市%' OR title LIKE '%Zootopia%'OR title LIKE '%動物方程式%';
UPDATE movie_2 SET Movie_ID = 6 Where title LIKE '%怪獸與牠們的產地%' OR title LIKE '%怪獸與他們的產地%';
UPDATE movie_2 SET Movie_ID = 7 Where title LIKE '%自殺突擊隊%' OR title LIKE '%suicide squad%';
UPDATE movie_2 SET Movie_ID = 8 Where title LIKE '%蝙蝠俠對超人%' OR title LIKE '%正義曙光%' OR title LIKE '%Batman v Superman%' OR title LIKE '%Dawn of Justice%';
UPDATE movie_2 SET Movie_ID = 9 Where title LIKE '%你的名字%'OR title LIKE '%君の名は%';
UPDATE movie_2 SET Movie_ID = 10 Where title LIKE '%出神入化2%' OR title LIKE '%Now You See Me 2%' OR title LIKE '%出神入化 2%';
UPDATE movie_2 SET Movie_ID = 11 Where title LIKE '%X戰警：天啟%' OR title LIKE '%天啟%'OR title LIKE '%X戰警%'OR title LIKE '%X-Men%'OR title LIKE '%XMen%';
UPDATE movie_2 SET Movie_ID = 12 Where title LIKE '%ID4%' OR title LIKE '%星際重生%';
UPDATE movie_2 SET Movie_ID = 13 Where title LIKE '%中場戰事%' OR title LIKE '%比利林恩%'OR title LIKE '%Billy Lynn%';
UPDATE movie_2 SET Movie_ID = 14 Where title LIKE '%葉問3%' OR title LIKE '%葉問 3%'OR title LIKE '%Ip Man 3%';
UPDATE movie_2 SET Movie_ID = 15 Where title LIKE '%寵物當家%' OR title LIKE '%The Secret Life of Pets%';
UPDATE movie_2 SET Movie_ID = 16 Where title LIKE '%神鬼認證%' OR title LIKE '%傑森包恩';
UPDATE movie_2 SET Movie_ID = 17 Where title LIKE '%海底總動員%' OR title LIKE '%多莉去哪兒%' OR title LIKE '%Finding Dory%';
UPDATE movie_2 SET Movie_ID = 18 Where title LIKE '%神鬼獵人%' OR title LIKE '%The Revenant%';
UPDATE movie_2 SET Movie_ID = 19 Where title LIKE '%寒戰2%' OR title LIKE '%寒戰 2%'OR title LIKE '%Cold War II%';
UPDATE movie_2 SET Movie_ID = 20 Where title LIKE '%厲陰宅2%' OR title LIKE '%厲陰宅 2%';
UPDATE movie_2 SET Movie_ID = 21 Where title LIKE '%魔獸%';
UPDATE movie_2 SET Movie_ID = 22 Where title LIKE '%我就要你好好的%' OR title LIKE '%Me Before You%';
UPDATE movie_2 SET Movie_ID = 23 Where title LIKE '%全面攻佔%' OR title LIKE '%倫敦救援%';
UPDATE movie_2 SET Movie_ID = 24 Where title LIKE '%怪奇孤兒院%' OR title LIKE '%孤兒院%';
UPDATE movie_2 SET Movie_ID = 25 Where title LIKE '%單身啪啪啪%' OR title LIKE '%How to Be Single%';
UPDATE movie_2 SET Movie_ID = 26 Where title LIKE '%薩利%' OR title LIKE '%哈德遜奇蹟%' OR title LIKE '%Sully%';
UPDATE movie_2 SET Movie_ID = 27 Where title LIKE '%樓下的房客%';
UPDATE movie_2 SET Movie_ID = 28 Where title LIKE '%神隱任務%' OR title LIKE '%永不回頭%';
UPDATE movie_2 SET Movie_ID = 29 Where title LIKE '%鋼鐵英雄%' OR title LIKE '%Hacksaw%';
UPDATE movie_2 SET Movie_ID = 30 WHERE title LIKE '%大尾鱸鰻%';

SELECT A.Movie_ID, B.Movie_Name
FROM movie_2 AS A, movie_ID AS B
WHERE A.Movie_ID = B.Movie_ID
GROUP BY A.Movie_ID;

SELECT count(*) FROM movie_2;
DELETE FROM movie_2 WHERE Movie_ID IS NULL;

SELECT count(*) AS 總評論數, ROUND(AVG(pos_add_neg),5) AS 平均正評加負評, 
ROUND(AVG(pos_less_neg),5) AS 平均正評減負評, 
ROUND(AVG(content_character),5) AS 平均內容字元數
FROM movie_2

SELECT count(*) AS 總評論數, ROUND(AVG(pos_add_neg),5) AS 平均正評加負評, ROUND(AVG(pos_less_neg),5) AS 平均正評減負評, ROUND(AVG(content_character),5) AS 平均內容字元數
FROM movie
Where (post_time BETWEEN '2016-10-28 00:00:00' AND '2016-11-04 23:59:59')
AND title LIKE '%奇異博士%' OR title LIKE '%奇博%'OR title LIKE '%Dr. Strange%'OR title LIKE '%Dr.Strange%'OR title LIKE '%Doctor Strange%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%美國隊長3%' OR title LIKE '%英雄內戰%'  OR title LIKE '%美隊3%'OR title LIKE '%美隊 3%'OR title LIKE '%captain america%' OR title LIKE '%civil war%'OR title LIKE '%美國隊長 3%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%死侍%' OR title LIKE '%惡棍英雄%'  OR title LIKE '%dead pool%'OR title LIKE '%deadpool%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%屍速列車%' OR title LIKE '%屍速%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%動物方城市%' OR title LIKE '%方城市%' OR title LIKE '%Zootopia%'OR title LIKE '%動物方程式%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%怪獸與牠們的產地%' OR title LIKE '%怪獸與他們的產地%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%自殺突擊隊%' OR title LIKE '%suicide squad%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%蝙蝠俠對超人%' OR title LIKE '%正義曙光%' OR title LIKE '%Batman v Superman%' OR title LIKE '%Dawn of Justice%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%你的名字%'OR title LIKE '%君の名は%';

SELECT *
FROM movie 
Where title LIKE '%出神入化2%' OR title LIKE '%Now You See Me 2%' OR title LIKE '%出神入化 2%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%X戰警：天啟%' OR title LIKE '%天啟%'OR title LIKE '%X戰警%'OR title LIKE '%X-Men%'OR title LIKE '%XMen%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%ID4%' OR title LIKE '%星際重生%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%中場戰事%' OR title LIKE '%比利林恩%'OR title LIKE '%Billy Lynn%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%葉問3%' OR title LIKE '%葉問 3%'OR title LIKE '%Ip Man 3%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%寵物當家%' OR title LIKE '%The Secret Life of Pets%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%神鬼認證%' OR title LIKE '%傑森包恩';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%海底總動員%' OR title LIKE '%多莉去哪兒%' OR title LIKE '%Finding Dory%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%神鬼獵人%' OR title LIKE '%The Revenant%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%寒戰2%' OR title LIKE '%寒戰 2%'OR title LIKE '%Cold War II%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%魔獸%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%我就要你好好的%' OR title LIKE '%Me Before You%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%全面攻佔%' OR title LIKE '%倫敦救援%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%怪奇孤兒院%' OR title LIKE '%孤兒院%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%單身啪啪啪%' OR title LIKE '%How to Be Single%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%薩利%' OR title LIKE '%哈德遜奇蹟%' OR title LIKE '%Sully%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%樓下的房客%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%大尾鱸鰻%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%神隱任務%' OR title LIKE '%永不回頭%';

SELECT count(*) AS 總評論數,AVG(pos_add_neg) AS 平均正評加負評, AVG(pos_less_neg) AS 平均正評減負評
FROM movie 
Where title LIKE '%鋼鐵英雄%' OR title LIKE '%Hacksaw%';

SELECT count(*)
FROM movie 
Where title LIKE '%雷%';

ALTER TABLE movie ADD tag1 int, ADD tag2 int, ADD tag3 int;
UPDATE movie SET tag1 = 1 WHERE title LIKE '%好雷%' 
OR title LIKE '%微好雷%'OR title LIKE '%好微雷%';
UPDATE movie SET tag2 = 1 WHERE title LIKE '%普雷%' OR title LIKE '%無雷%';
UPDATE movie SET tag3 = 1 WHERE title LIKE '%負雷%' OR title LIKE '%吐槽%'
OR title LIKE '%糞雷%' OR title LIKE '%蟑螂雷%'OR title LIKE '%微負雷%'
OR title LIKE '%負微雷%';

SELECT sum(tag1) as '好雷篇數', sum(tag2) as '普雷篇數',sum(tag3) AS '負雷篇數'
FROM movie;

SELECT id,CHARACTER_LENGTH(content) AS 'character length'
FROM movie
WHERE tag1 = 1;
SELECT id,CHARACTER_LENGTH(content) AS 'character length'
FROM movie
WHERE tag2 = 1;
SELECT id,CHARACTER_LENGTH(content) AS 'character length'
FROM movie
WHERE tag3 = 1;
SELECT id, length(content) AS content_length
FROM movie;
ALTER TABLE movie ADD content_character INT;
UPDATE movie SET content_character=CHARACTER_LENGTH(content);

ALTER TABLE movie ADD review_type VARCHAR(6);
UPDATE movie 
SET review_type = 'good'
WHERE tag1=1;
ALTER TABLE movie ADD review_type VARCHAR(6);
UPDATE movie
SET review_type = 'normal'
WHERE tag2=1;
ALTER TABLE movie ADD review_type VARCHAR(6);
UPDATE movie
SET review_type = 'bad'
WHERE tag3=1;

SELECT id, post_time, author,positive_score,negative_score, round(pos_add_neg,4) AS pos_add_neg, 
round(pos_less_neg,4) AS pos_less_neg, content_character,review_type
FROM movie
WHERE review_type IS NOT NULL;

SELECT A.movie_ID AS 票房排名,B.Movie_Name AS 電影名稱,B.movie_date AS 上映日期,B.one_week_date AS 一周後日期,count(*) AS 總評論數, 
ROUND(AVG(A.pos_add_neg),5) AS 平均正評加負評, 
ROUND(AVG(A.pos_less_neg),5) AS 平均正評減負評, 
ROUND(AVG(A.content_character),5) AS 平均內容字元數
FROM movie_2 AS A, movie_ID AS B
Where (A.post_time BETWEEN B.movie_date AND B.one_week_date) AND A.content_type = 'main' AND A.movie_ID = B.movieID
GROUP BY movieID;

SELECT A.movie_ID AS 票房排名,count(*) AS 純回應總數,B.Movie_Name AS 電影名稱,
ROUND(AVG(A.positive_score),5) AS 純回應_平均正評,
ROUND(AVG(A.negative_score),5) AS 純回應_平均負評, 
ROUND(AVG(A.pos_add_neg),5) AS 純回應_平均正評加負評, 
ROUND(AVG(A.pos_less_neg),5) AS 純回應_平均正評減負評, 
ROUND(AVG(A.content_character),5) AS 純回應_平均內容字元數
FROM movie_2 AS A, movie_ID AS B
Where (A.post_time BETWEEN B.movie_date AND B.one_week_date) AND A.mo_type = 'G' AND A.movie_ID = B.movieID
GROUP BY movieID;

UPDATE movie_2 SET pos_add_neg = positive_score + negative_score;
UPDATE movie_2 SET pos_less_neg = positive_score - negative_score; 

SELECT *
FROM movie_id
WHERE movieID = '1';
```
