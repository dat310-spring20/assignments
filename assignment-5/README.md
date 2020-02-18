# Assignment 5 - Gradebook

You task is to write a flask application in python that shows students, courses and grades.

The application uses three files to store data.

### Input

The three input files are called `grades.tsv`, `courses.tsv`, and `students.tsv`. These contain data in tab-separated format.

The `grades.tsv` file has the following format (`{}` denote variables):
```
{student_no} {course_code} {grade}
```
I.e., each line is a grade of a certain person on a specific course.

  - `student_no` is a numerical value
  - `course_code` has the format `XXXYYY` where `X` is a capital letter (`[A..Z]`) and `Y` is a digit (`[0..9]`)
  - `grade` is a value in the `A..F` range

The `courses.tsv` file contains the names of courses, one line per course:
```
{course_code} {course_name}
```

The `students.tsv` file contains the names of students, one line per student:
```
{student_no} {student_name}
```


### Output

You should complete the `app.py` flask application. Generate a pages as shown in the sample. You need to create the following templates/routes:

  - `/` or `index.html`
    * This file contains an overview and links to all files. Specifically, there should be two tables:
        - List of all courses, with columns "course code" and "name", sorted by course code. Add a link on the course code to the course's page.
        - List of all students, with columns "student no" and "name", sorted by student number. Add a link on the student number to the student's profile page.
        - A link to a form that allows to add new students.   
        - See e.g. [index.html](sample/index.html)  
  - `/student/{student_no}`
    * This page displays for a student with a given student number:
        - The name of the student.
        - A list (table) of all courses (with course code and name) together with the grade.
        - A form with button that to add more grades for this student.
        - See e.g. [111111.html](sample/student/111111.html)
  - `/course/{course_code}`
    * This page displays for course with course_code
        - The course code.
        - A list (table) of all students that have a grade from this course, and their grades.
        - A summary of the grades, i.e. a table with the count of each grade.
        Only including grades with count 1 or higher.
        - A link to add more grades.
        - See e.g. [DAT100.html](sample/course/DAT100.html)
  - `/add_student`  
    * This page displays a form, that allows to add a student.
        - The form has one field for the students name.
        - When submitted, check that the name in not empty. Otherwise, display an error [student_form_error](sample/student_form_error.html).
        - Otherwise, add the student to `students.tsv` with a new student_no.
        - Then redirect the user to the index page.
        - See e.g. [student_form.html](sample/student_form.html).
  - `/add_grade`
    * This page allows to add a grade for a given course and student.
        - It contains a dropdown with all students.
        - It contains a dropdown with all courses.
        - It contains a dropdown with grades A to F.
        - It contains a submit button.
        - All dropdowns contain default elements, i.e. *Select*.
        - If the form is submitted and course, student or grade is missing,
        display the form again, together with an error message ([add_grade_error.html](sample/add_grade_error.html))
        - If a grade is successfully added to `grades.tsv` display a success message ([add_grade_success.html](sample/add_grade_success.html))
        - Display a link back to the main page.
        - See e.g. [add_grade.html](sample/add_grade.html).

  - `/add_grade` from course or student:
    * When the form is reached from a given course, then the Course-select should only contain this one course. E.g. [add_grade_DAT100.html](sample/add_grade_DAT100.html).
    * When the form is reached from a given student, then the student-select should only contain this one student. E.g. [add_grade_stud1.html](sample/add_grade_stud1.html).

All templates should inherit from one base template `base.html`, that contains header and footer of the HTML page.
The CSS file `/static/style.css` is already given (but you are free to make changes to it, if you wish). 

You may assume that the three input files (`grades.tsv`, `courses.tsv`, `students.tsv`) are in the same folder as the `app.py` file and that their content is valid (i.e., follows the above format).

Under the `sample` folder, you can find an example of how the page may look.

# Øving 6 - Karakterbok

Du skal skrive en flask applikasjon i python som viser studenter, kurs og karakterer.

Applikasjonen bruker tre filer for å lagre data.

### Input

De tre inputfilene kalles `grades.tsv`, `courses.tsv`, og `students.tsv`. Disse filene inneholder data i et 'tab'-separert format.

`grades.tsv` filen har følgende struktur, hvor `{}` inneholder variablene.
```
{student_no} {course_code} {grade}
```

Hver linje innheolder karakteren som en person fikk i et fag, ved et gitt semester.

  - `student_no` er et tall
  - `course_code` har formatet `XXXYYY`, hvor `X` er en stor bokstav (`[A..Z]`) og `Y` er et siffer (`[0..9]`)
  - `grade` har er en karakterer, A-F

`courses.tsv` filen inneholder navnene til kursene, en linje per kurs:
```
{course_code} {course_name}
```

`student.tsv` filen inneholder navenen til studentene, en linje per student:
```
{student_no} {student_name}
```

### Output

Fullfør applikasjonen i `app.py`. Generer sidene som vist i `sample` folderen. Du skal lage følgende templates/routes:

  - `/` route med template `index.html`
    * Denne filen inneholder en oversikt og linker til alle filer. Det skal være tre tabeller:
        - Liste over alle emner, med kollonene "course code" og "name", sortert etter "course code". Legg til en link på emnekoden til emnets side.
        - Liste over alle studenter, med kollonene "student no" og "name", sortert etter "student no". Legg til en link på studentnummeret til studentens profilside
        - En lenke til et skjema som gjør det mulig å legge til nye studenter.
        - Se [index.html](sample/index.html)  
  - `/student/{student_no}`
    * Denne siden viser for hver student med en gitt student nummer:
        - Studentens navn.
        - En liste (tabell) over alle emner (med emnekode), sammen med karakter
        - Et form med en knapp, der man kommer til et annet form, og kan legge til flere karakterer for denne studenten.
        - Se e.g. [111111.html](sample/student/111111.html)
  - `/course/{course_code}`
    * Denne siden viser for et emne med gitt course_code
        - Koden course_code.
        - En liste (tabell) over alle studenter med en karakter fra dette emne og deres karakter.
        - En karakter sammenfatning, i.e. en tabell med antall av hver karakter gitt.
        Bare inkluder karakterer med antall større en 0.
        - En lenke for å legge til flere karakterer for dette kurset.
        - Se e.g. [DAT100.html](sample/course/DAT100.html)
  - `/add_student`  
    * Denne siden viser et skjema som tillater å legge til studenter.
        - Skjemaet har et felt (input) for studentens navn.
        - Ved innsending, sjekk at navnet ikke er tomt. Ellers vis en error [student_form_error](sample/student_form_error.html).
        - Legg til studenten i `students.tsv` med et nytt student_no.
        - Etterpå send brukeren tilbake til `/` (redirect).
        - Se e.g. [student_form.html](sample/student_form.html).
  - `/add_grade`
    * Denne siden tillater å legge til en karakter for et emne og en student.
        - Siden inneholder en select med alle studenter.
        - Siden inneholder en select med alle emner.
        - Siden inneholder en select med karakterer A til F.
        - Siden inneholder en submit knapp.
        - Alle selecter inneholder default elementer, i.e. *Select*.
        - Om skjemaet sendes inn med et default element valgt, vis formen igjen, sammen med en feil ([add_grade_error.html](sample/add_grade_error.html))
        - Om karakteren blir lagt til i `grades.tsv`, vis en success melding ([add_grade_success.html](sample/add_grade_success.html))
        - Vis en lenke for å komme tilbake til hovedsiden.
        - Se e.g. [add_grade.html](sample/add_grade.html).

  - `/add_grade` fra emne eller student:
    * Hvis brukeren kommet til dette skjema gjennom å trykke på knappen på siden til et emne, skal emne select kun inneholder dette emne.
    E.g. [add_grade_DAT100.html](sample/add_grade_DAT100.html).
    * Hvis brukeren kommet til dette skjema gjennom å trykke på knappen på siden til en student, skal student selecten kun inneholder denne studenten.
    E.g. [add_grade_stud1.html](sample/add_grade_stud1.html).

Alle templates skal arve fra et base template `base.html`, som inneholder header og footer til en HTML side.
CSS filen `static/style.css` er allerede gitt (men du må gjerne gjøre forandringer, om du vil).

Du kan anta at de tre filnene (`grades.tsv`, `courses.tsv`, `students.tsv`) ligger i samme mappa som `app.py` filen og at deres innhold er korrekt (i.e. følger riktig formattering).

I `sample` mappen finner du et eksempel av hvordan siden skal se ut.
