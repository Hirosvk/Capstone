# html API
## Root
### GET /
  * static_page loads React App

# JSON API

## users

## session
### GET /session/new
  * log-in page

### POST /session/
  * log-in

### DELETE /session/
  * log-out


### POST /api/user/
* signup
  * login user
  * return currentUser on success
  * return full error messages on failure

### GET /api/user/
* require_current_user
* return names and id's of...
  * klasses enrolled by the current_user
  * klasses created by the current_user
  * study_sets created by the current_user

### GET /api/user/test_scores
* require_current_user
* return test scores of the current_user


## klasses
### GET /api/klasses/;id
  * return klass info (id, name, description, teacher's username, created_at, current_user's enrollment status, and enrollment_id)

### GET /api/klasses/:id/study_sets
  * return Study Sets of the Klass (name, id)

### GET /api/klasses/:id/by_study_set
  * return test scores grouped by study set
    * require current_user == teacher

### GET /api/klasses/:id/by_student
  * return test scores grouped by student
    * require current_user == teacher

### POST /api/klasses/new
  * create new klass with current_user.id as teacher_id
  * params: klass_name, description, class_ids
    * require log-in

## enrollments
### DELETE /api/enrollments/:id
  * delete a row from enrollments table
    * require log-in && current_user != teacher

### POST /api/enrollments/
  * create new row in enrollments table with current_user_id
  * params: class_id
    * require log-in && current_user != teacher


## study_sets
### GET /api/study_sets/
  * return StudySets created by all users

### GET /api/study_sets/:id
  * return single Study Set (name, creator's username, created_at, updated_at)
  * return all the words of the Study Set in a nested hash

### DELETE /api/study_sets/:id
  * delete the study set
    * require current_user == creator

### POST /api/study_sets/
  * create new study_set with current_user.id as creator_id
  * create new words
  * params: study_set_name, klass_ids as array, words as a hash map(key: word_english, val: word_foreign)
    * require log-in

## test_records
### POST /api/test_records
* submit test score (create new test_record) with current_user.id as user_id
* params: study_set_id, score
  * require log-in

## search
### GET /api/search?=[search_text]
* query search_text in DB for study_set_name, word, and class_name, and return results grouped by study set and class
