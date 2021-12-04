# Task 2
#### Query:
```sql
SELECT CONCAT("This is ", name, IF(gender="m", ", he ", ", she ")), "has email ", email) AS info FROM users;
```
#### Result:
	+-----------------------------------------------+
	| info                                          |
	+-----------------------------------------------+
	| This is Vasya, he has email mmm@mmail.com     |
	| This is Alex, he has email mmm@gmail.com      |
	| This is Alexey, he has email alexey@gmail.com |
	| This is Helen, she has email hell@gmail.com   |
	| This is Jenny, she has email eachup@gmail.com |
	| This is Lora, she has email tpicks@gmail.com  |
	+-----------------------------------------------+
# Task 3
#### Query:
```sql
SELECT CONCAT("We have ", COUNT(gender), IF(COUNT(gender)=1, " boy!", " boys!")) AS "Gender information:" FROM users WHERE gender="m" UNION SELECT CONCAT("We have ", COUNT(gender), IF(COUNT(gender)=1, " girl!", " girls!")) AS "Gender information:" FROM users WHERE gender="f";
```
#### Result:
	+---------------------+
    | Gender information: |
    +---------------------+
    | We have 3 boys!     |
    | We have 3 girls!    |
    +---------------------+
# Task 5
#### Query:
```sql
SELECT vocabulary.name, COUNT(words.id) AS words FROM vocabulary LEFT JOIN words ON vocabulary.id=words.vocabulary_id GROUP BY vocabulary.name;
```
#### Result:
	+---------+-------+
    | name    | words |
    +---------+-------+
    | animals |    10 |
    | school  |    10 |
    | nature  |    10 |
    | human   |    10 |
    | SF      |    10 |
    +---------+-------+

