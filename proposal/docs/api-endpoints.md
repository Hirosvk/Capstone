# html API
## Root
* GET /
  * static_page loads React App

## user
* GET /user/new
  * sign-in page
* POST /user
  * create new user

## session
* GET /session/new
  * log-in page
* POST /session/
  * log-in
  * redirects to GET /
* DELETE /session/
  * log-out
  * redirects to GET /


# JSON API

## users
### GET /api/user/navbar_data
* return names and id's of...
  * klasses enrolled by the current_user
  * klasses created by the current_user
  * study sets created by the current_user
### GET /api/user/test_scores
* return test scores of the current_user

## klasses
### GET /api/klasses/:id/study_sets
  * return Study Sets of the Klass (name, id)
### GET /api/klasses/:id/by_study_set
  * return test scores grouped by study set
    * require current_user == teacher
### GET /api/klasses/:id/by_student
  * return test scores grouped by student
    * require current_user == teacher
    * toggle enrollment status
* create new klass
  * require log-in


### DELETE /api/klassses/:id/enrollment
  * delete a row from enrollments table
    * require log-in && current_user != teacher
### POST /api/klasses/:id/enrollment
  * create new row in enrollments table
    * require log-in && current_user != teacher


## study_sets
* return single Study Set
* return all the words of the Study Set
* create new study_set
  * require log-in

## test_records
* submit test score (create new test_record)
  * require log-in

## search
* query search text in DB for language, study_set name, word, and class, and return results
