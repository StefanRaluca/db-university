### 1. Selezionare tutti gli studenti nati nel 1990 
 # soluzione : SELECT * FROM students WHERE year(date_of_birth) = 1990;
   - Showing rows 0 - 24 (160 total, Query took 0.0034 seconds.)


### 2.Selezionare tutti i corsi che valgono più di 10 crediti
 # soluzione : SELECT* FROM courses WHERE cfu > 10;
   - Showing rows 0 - 24 (479 total, Query took 0.0023 seconds.)

### 3.Selezionare tutti gli studenti che hanno più di 30 anni
 # soluzione : SELECT * FROM students WHERE TIMESTAMPDIFF(YEAR, date_of_birth, CURDATE()) > 30;
   -  Showing rows 0 - 24 (3541 total, Query took 0.0005 seconds.)

### 4.Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea 
  # soluzione : SELECT * FROM courses WHERE period ='I semestre' and year = 1;
    - Showing rows 0 - 24 (286 total, Query took 0.0009 seconds.)
   
### 5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020
 # soluzione : SELECT * FROM exams WHERE date = '2020-06-20' AND HOUR(hour) >= 14;
   -  Showing rows 0 - 20 (21 total, Query took 0.0027 seconds.)
### 6.Selezionare tutti i corsi di laurea magistrale
 # soluzione : SELECT * FROM degrees WHERE level = 'magistrale';
   -  Showing rows 0 - 24 (38 total, Query took 0.0019 seconds.)
### 7.Da quanti dipartimenti è composta l'università?
 # soluzione : SELECT COUNT(*) AS total_departments FROM departments;
   -  total_departments - 12; Query results operations . 
### 8.Quanti sono gli insegnanti che non hanno un numero di telefono?
 # soluzione : SELECT COUNT(*) AS teacher_without_phone FROM teachers WHERE phone IS NULL;
   - teacher_without_phone -50; Query results operations . 