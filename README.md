# SQL_First

### Основные запросы SELECT:

1:
```sql
-- 1. Вывести идентификаторы курсов (предметов):

SELECT CourseId FROM Course
```

2:
```sql
-- 2. Вывести всю информацию о курсах (предметах):

SELECT * FROM COURSE
```


### Запросы с условием WHERE:

3:
```sql
-- 3. Вывести идентификатор курса с названием "Machine Learning":

SELECT CourseId FROM Course WHERE CourseTitle = 'Machine Learning'
```

4:
```sql
-- 4. Вывести название курса с идентификатором 5:

SELECT CourseTitle FROM Course WHERE CourseId = 5
```

5:
```sql
-- 5. Вывести список мобильных телефонов (PhoneType = 'cell') из таблицы "PHONE_LIST":

SELECT Phone FROM PHONE_LIST WHERE PhoneType = 'cell'
```


### Агрегатные функции:

6:
```sql
-- 6. Вывести количество отметок, которое получил студент с идентификатором (номером зачетки) 345576:

SELECT count(Grade) FROM EXAM_RESULT WHERE StudentId = 345576
```

7:
```sql
-- 7. Вывести номера зачеток (идентификаторы студентов) и средние баллы, которые получили студенты за все экзамены:

SELECT StudentId, AVG(Grade) FROM EXAM_RESULT GROUP BY StudentId
```

8:
```sql
-- 8. Вывести минимальный и максимальный баллы, полученные студентами на экзаменах:

SELECT MAX(Grade), MIN(Grade) FROM EXAM_RESULT
```


### Объединение и пересечение:

9:
```sql
-- 9. Найти пересечение идентификаторов студентов, получавших и 2, и 5. Каждый идентификатор из пересечения должен встречаться не более одного раза:

SELECT StudentId FROM EXAM_RESULT WHERE Grade = 2
INTERSECT
SELECT StudentId FROM EXAM_RESULT WHERE Grade = 5
```

10:
```sql
-- 10: Найти объединение идентификаторов студентов, у которых есть хоть одна 2 и/или хоть одна 5. Каждый идентификатор из пересечения должен встречаться не более одного раза:

SELECT StudentId FROM EXAM_RESULT WHERE Grade = 2
UNION
SELECT StudentId FROM EXAM_RESULT WHERE Grade = 5
```

Слелано с помощью `https://sqliteonline.com/`.
