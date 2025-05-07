# 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```
SELECT 
	students.* ,degrees.*
FROM
    students
        INNER JOIN
    degrees ON degrees.id = students.degree_id
    WHERE degrees.name = 'corso di laurea in economia'
```



# 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
```
SELECT 
    *
FROM
    db_university.degrees
        INNER JOIN
    departments ON departments.id = degrees.department_id
    WHERE degrees.level = 'magistrale'
    AND departments.name = 'dipartimento di neuroscienze'
```
# 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```
SELECT 
    *
FROM
    db_university.teachers
    INNER JOIN course_teacher on teachers.id = course_teacher.teacher_id
    INNER JOIN courses on course_teacher.course_id = courses.id
    WHERE teachers.id = 44

```


# 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
```
SELECT 
    *
FROM
    db_university.students
    INNER JOIN degrees on students.degree_id = degrees.id
    INNER JOIN departments on degrees.department_id = department_id
    ORDER BY students.surname ,students.name
```
# 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
```
SELECT 
    courses.*,teachers.*,degrees.*
FROM
    db_university.teachers
    INNER JOIN course_teacher on teachers.id = course_teacher.teacher_id
    INNER JOIN courses on course_teacher.course_id = courses.id
	INNER JOIN degrees ON degrees.id = courses.degree_id
```



# 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
```
SELECT 
    *
FROM
    db_university.teachers
    INNER JOIN course_teacher on teachers.id = course_teacher.teacher_id
    INNER JOIN courses on course_teacher.course_id = courses.id
	INNER JOIN degrees ON degrees.id = courses.degree_id
    INNER JOIN departments on departments.id = degrees.department_id
    WHERE departments.name = 'dipartimento di matematica'

```

# 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.