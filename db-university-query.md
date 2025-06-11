### Selezionare tutti gli studenti nati nel 1990

SELECT \* FROM db_university.students
WHERE date_of_birth >= '1990-01-01'
AND date_of_birth <= '1990-12-31';

### Selezionare tutti i corsi che valgono più di 10 crediti

SELECT \* FROM db_university.courses
WHERE cfu > 10;

### Selezionare tutti gli studenti che hanno più di 30 anni

SELECT \* FROM db_university.students
WHERE date_of_birth < '1995-06-11';

### Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea

SELECT \* FROM db_university.courses
WHERE period = "I semestre"
AND year = 1;

### Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio del 20/06/2020

SELECT \* FROM db_university.exams
WHERE hour > "14:00:00"
AND date = "2020-06-20";

### Selezionare tutti i corsi di laurea magistrale

SELECT \* FROM db_university.degrees
WHERE level = "magistrale";

### Da quanti dipartimenti è composta l'università?

SELECT COUNT(\*) FROM db_university.departments;

### Quanti sono gli insegnanti che non hanno un numero di telefono?

SELECT COUNT(\*) FROM db_university.teachers
WHERE phone IS NULL;
