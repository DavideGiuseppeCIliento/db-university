### Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT \*
FROM `students`
INNER JOIN `degrees`
ON `degrees`.`id`= `students`.`degree_id`
WHERE `degrees`.`name` = "Corso di Laurea in Economia";

### Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT \*
FROM `degrees`
INNER JOIN `departments`
ON `departments`.`id`= `degrees`.`department_id`
WHERE `departments`.`name` LIKE "%Neuroscienze";

### Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT \*

FROM `courses`

INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`

INNER JOIN `teachers`
ON `teachers`.`id` = `course_teacher`.`teacher_id`

WHERE `teachers`.`name` = "Fulvio" AND `teachers`.`surname` = "Amato";

### Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT
`students`.`name`,
`students`.`surname`,
`degrees`.`name`,
`departments`.`name`

FROM `students`

INNER JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`

INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`

ORDER BY `students`.`name` ASC, `students`.`surname` ASC;

### Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT
`degrees`.`name`,
`courses`.`name`,
`teachers`.`name`,
`teachers`.`surname`

FROM `degrees`

INNER JOIN `courses`
ON `degrees`.`id` = `courses`.`degree_id`

INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`

INNER JOIN `teachers`
ON `teachers`.`id` = `course_teacher`.`teacher_id`;

### Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

### BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente,
