## users
column names    | Data Type | Details
----------------|-----------|---------------------
id              | integer   |    
username        | string    | null: false, unique: true  
password_hash   | string    | null: false, unique: true
email           | string    | null: false  unique: true
session_token   | string    | null: false, unique: true

- user has many
  - sets_created
  - sets_studied
  - test_taken(test_completed, test_in_progress)
  - created_classes
  - enrolled_classes

## study_sets
column names    | Data Type | Details
----------------|-----------|---------------------
id              | integer   |    
study_set_name  | string    | null: false
creator_id      | integer   | null: false, indexed
language_id     | integer   | null: false, indexed


- study_set belongs to
  - creator(user)
  - language
- study_set has many
  - study_set_words
  - students
  - test_records
  - classes

## study_set_words
column names    | Data Type | Details
----------------|-----------|---------------------
id              | integer   |   
language_id     | integer   | null: false, indexed
word_english    | string    | null: false
word_foreign    | string    | null: false

- study_set_word belongs to study_set


## study_records
When logged-in users use any feature of the study set, it is recorded on this table.

column names    | Data Type | Details
----------------|-----------|---------------------
id              | integer   |
user_id         | integer   | null: false, indexed
study_set_id    | integer   | null: false, indexed

- study_record belongs to
  - user
  - study_set

## test_records
column names    | Data Type | Details
----------------|-----------|---------------------
id              | integer   |
user_id         | integer   | null: false, indexed
study_set_id    | integer   | null: false, indexed
score           | integer   | null: false, (in %, btw 0 and 100)
completed       | boolean   | default: false

- test_record belongs to
  - user
  - study_set

## classes
column names    | Data Type | Details
----------------|-----------|---------------------
id              | integer   |
language_id     | integer   | null: false, indexed
class_name      | string    | null: false
description     | text      |
teacher_id      | integer   | null: false, indexed

- belongs to
  - teacher
  - language
- has many
  - students
  - study_sets

## class_set_joins
column names    | Data Type | Details
----------------|-----------|---------------------
id              | integer   |
class_id        | integer   | null: false,
study_set_id    | integer   | null: false, class/set unique pair

- belongs to
  - study_set
  - class

## class_student_joins
column names    | Data Type | Details
----------------|-----------|---------------------
id              | integer   |
class_id        | integer   | null: false
student_id      | integer   | null: false, class/student unique pair

- belongs to
  - class
  - student(user)


## languages
column names    | Data Type | Details
----------------|-----------|---------------------
id              | integer   |
language        | string    | null: false

- language has many
  - classes
  - study_sets
