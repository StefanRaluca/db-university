## Group by
### 1. Contare quanti iscritti ci sono stati ogni anno
# soluzione : SELECT YEAR(enrolment_date) AS year, COUNT(*) AS total_students FROM students GROUP BY YEAR(enrolment_date);
   - year	total_students	
2018      -   912
2019      -  1709
2020      -  1645
2021      -   734

### 2.Contare gli insegnanti che hanno l'ufficio nello stesso edificio
 # soluzione : SELECT office_address, COUNT(*) AS num_teachers FROM teachers GROUP BY office_address;
 -  Mostro le righe 0 - 24 (29 del totale, La query ha impiegato 0,0014 secondi.)
 ### 3.Calcolare la media dei voti di ogni appello d'esame
 # soluzione : SELECT exam_id, AVG(vote) AS average_vote FROM exam_student GROUP BY exam_id;
  -  Mostro le righe 0 - 24 (4078 del totale, La query ha impiegato 0,0046 secondi.)
### 4. Contare quanti corsi di laurea ci sono per ogni dipartimento
 # soluzione :  SELECT department_id, COUNT(*) AS total_degree FROM degrees GROUP BY department_id;
  - department_id  -	total_degree
    1	                    10	
    2	                    4	
    3	                    4	
    4	                    9	
    5	                    4	
    6	                    6	
    7	                    7	
    8	                    8	
    9	                    5	
    10	                    8	
    11	                    3	
    12	                    7	

##  Joins

### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
  # soluzione : SELECT students.* FROM students JOIN degrees ON students.degree_id = degrees.id JOIN departments ON degrees.department_id = departments.id WHERE departments.name = 'Dipartimento di Scienze economiche e aziendali';
    - Mostro le righe 0 - 24 (336 del totale, La query ha impiegato 0,0043 secondi.)
### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
 # soluzione : SELECT * FROM degrees JOIN departments ON degrees.department_id = departments.id WHERE departments.name = 'Dipartimento di Neuroscienze';
   -  Mostro le righe 0 - 6 (7 del totale, La query ha impiegato 0,0007 secondi.)
### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
  # soluzione : SELECT courses.* FROM courses JOIN course_teacher ON courses.id = course_teacher.course_id JOIN teachers ON course_teacher.teacher_id = teachers.id WHERE teachers.id= '44';
   -  Mostro le righe 0 - 10 (11 del totale, La query ha impiegato 0,0053 secondi.)
### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
 # soluzione : SELECT students.name, students.surname, degrees.name AS degree_name, departments.name AS department_name FROM students JOIN degrees ON students.degree_id = degrees.id JOIN departments ON degrees.department_id = departments.id ORDER BY students.surname, students.name;
  -  Mostro le righe 0 - 24 (5000 del totale, La query ha impiegato 0,0357 secondi.) [surname: AMATO... - AMATO...] [name: BRIGITTA... - MANFREDI...]
### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
 # soluzione : SELECT degrees.name AS degree_name, courses.name AS course_name, teachers.name AS teacher_name, teachers.surname AS teacher_surname FROM degrees JOIN courses ON degrees.id = courses.degree_id JOIN course_teacher ON courses.id = course_teacher.course_id JOIN teachers ON course_teacher.teacher_id = teachers.id ORDER BY degrees.name, courses.name;
  - Mostro le righe 0 - 24 (1317 del totale, La query ha impiegato 0,0197 secondi.)