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
