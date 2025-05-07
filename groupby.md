# 1. Contare quanti iscritti ci sono stati ogni anno
```
SELECT 
    count(*) , year(enrolment_date) as year_iscription
FROM
    db_university.students
    GROUP BY year_iscription
    order by year_iscription
```


# 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```
SELECT 
   count(*) , office_address
   FROM
    db_university.teachers
    GROUP BY office_address
```

# 3. Calcolare la media dei voti di ogni appello d'esame
```
SELECT 
    avg(vote), exam_id
FROM
    db_university.exam_student
    GROUP BY exam_id
```



# 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```
SELECT 
    COUNT(*), degree_id
FROM
    db_university.courses
GROUP BY degree_id
```
