# README

## Module 2 Rails Review

## Models
Student -< Enrollment >- Course 

Student has many enrollments, student has many courses through enrollments
Course has many enrollments, course has many students through enrollments 
Enrollment belongs to a student and a course

## Pre-Setup (This step has already been done)
- `rails g model Student name age:integer --no-test-framework`
- `rails g model Course name teacher_name --no-test-framework`

- `rails g controller students index new create show edit update destroy`
- `rails g controller courses index`


## Setup
- `rails g model Enrollment student_id:integer course_id:integer --no-test-framework`
- `rails g controller enrollments`
- `rails db:create`
- `rails db:migrate`
- `rails db:seed`

### Deliverables 

1. Display all students in the database
2. Add new students
3. Have a show page for each student
4. Ability to register for a new course using form_for and collection_select by creating a new enrollment. 
5. In the show page, the courses associated with the student are displayed.
6. In the show page, we have the ability to update or delete the specific student.
7. Ability to drop course by deleting enrollment.

### Bonus
- When creating a new student, add validations to ensure that they have a name and age. 
- If it is not valid, display the errors. 
