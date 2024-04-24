## DB
Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni Corso può essere tenuto da diversi Insegnanti;
ogni Corso prevede più appelli d'Esame;
ogni Studente è iscritto ad un solo Corso di Laurea;
ogni Studente può iscriversi a più appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente. Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.



### departments
- id BIGINT | UNIQUE | AI | PK | INDEX | 
- name VARCHAR(25) | NOTNULL
### degree_courses
- id BIGINT | UNIQUE | AI | PK | INDEX
- name VARCHAR(40) | NOTNULL
- id_department FK | BIGINT | 
### courses
- id BIGINT | UNIQUE | AI | PK | INDEX
- name_course VARCHAR(40) | NOTNULL
- id_degree_courses FK | BIGINT 
- address VARCHAR(100) | NULL
### teachers
- id BIGINT | UNIQUE | AI | PK | INDEX
- name VARCHAR(25) | NOTNULL
- lastname VARCHAR(25) | NOTNULL
- cfu CHAR(16) | NULL
- id_course FK | BIGINT | 
### exam_calls
- id BIGINT | UNIQUE | AI | PK | INDEX
- id_course FK | BIGINT 
- subject VARCHAR(25) | NOTNULL
- date DATATIME | NOTNULL
### students
- id BIGINT | UNIQUE | AI | PK | INDEX
- name VARCHAR(25) | NOTNULL
- lastname VARCHAR(25) | NOTNULL
- id_degree_corse FK | BIGINT 
- photo VARCHAR(255) | NULL
### registration_exams
- id BIGINT | UNIQUE | AI | PK | INDEX
- id_exam_calls FK | BIGINT 
- id_student FK | BIGINT 
- vote TINYINT | NOTNULL