# Course Registration Application

## Module 2 Rails Review 
For this challenge, you'll be working with a Course Registration domain.

In this repo, there is a Rails application with some features built out. Your job is to extend this code to add the functionality described in the deliverables below.

## Models (The Domain)
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
Before you begin coding your solution, fork this repo and then cd into it. Generate the model necessary (a sample generator is provided below. You can also use `rails g resource`). Then run bundle install, rails db:migrate, and rails db:seed to install dependencies and set up the database, and run rails s to start the server.

- `rails g model Enrollment student_id:integer course_id:integer --no-test-framework`
- `rails g controller enrollments`
- `bundle install`
- `rails db:create`
- `rails db:migrate`
- `rails db:seed`
- `rails s`

## What You Already Have

The starter code includes migrations, models, and seed data for Student and Course. There are also controller actions, and views to support listing the students and courses.

After running the setup instructions above, visiting `'/students'` will display all of the students, and visiting `'/courses'` will display all of the courses.

***Schema***

Students

| Column | Type |
| ------------- | ------------- |
| name  | String  |
| age  | Integer  |
| created_at  | DateTime  |
| updated_at  | DateTime  |

Courses

| Column | Type |
| ------------- | ------------- |
| name  | String  |
| created_at  | DateTime  |
| updated_at  | DateTime  |

## Deliverables 
Update the code of the application to meet the following deliverables. Follow RESTful naming conventions and the MVC pattern to divide responsibility.

***Read through these deliverables carefully to understand the requirements for this code challenge. Tackle them one by one, as they build on each other sequentially.***

### 1. Display all students in the database
Display students' names in the index page. Set up a link_to so that when clicking on the names, we are redirected to the student show page.

### 2. Have a show page for each student
Display the student's name and age in the show page.

### 3. Add new students
A user can fill out a form to add a new student to the database. After submitting and creating, we should be redirected to the students index page.

### 4. Ability to register for a new course using form_for and collection_select by creating a new enrollment. 
A user can fill out a form to create a new enrollment. They can:

- Choose an existing student from a select dropdown
- Choose an existing course from a select dropdown
- Submit the form

After submitting and creating the enrollment, redirect to the selected STUDENT's show page.

### 5. In the show page, the courses associated with the student are displayed.
Make changes to the show page to show the courses the student has enrolled in. 

### 6. In the show page, we have the ability to update or delete the specific student.
Make changes to the show page to have a link_to or button_to for updating OR deleting a student. (Try both as a bonus).

### 7. Ability to drop course by deleting enrollment (Bonus).
Make changes to the show page to add a link_to or button_to next to each course in a student's show page. The goal is to drop that course. HINT: What SHOULD you be deleting in the database?

### Bonus
- When creating a new student, add validations to ensure that they have a name and age. 
- If it is not valid, display the errors. 
