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
