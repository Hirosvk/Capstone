### Flux Cycles

## Stores
* SearchResultStore
* MyClassStore
* MyStudySetStore
* RecentActivityStore
* StudySetIndexStore
* ProgressByStudySetStore
* ProgressByStudentStore
* WordStore
* TestScoreStore

## Search Cycle
# Search
  state: search text
  Make API requests for matching study sets/classes
    --> store the response
      --> emit change to SearchResult
# SearchResults
  on mount, add listener to SearchResultStore
  receives search results and pass each one as prop
# SearchResultItem
  props: result item
  render link to class/study Set



## Navbar Cycle

# Navbar
  On mount, fetch Users' classes and study set data
  --> store
    --> emit change to MyClassIndex and MyStudySetIndex

# MyClassesIndex
  state: my classes data
  On mount, add listener to MyClassIndexStore
  receives data from MyClassStore
  render links to the classes

# MyStudySetIndex
  state: my study sets data
  On mount, add listener to MyStudySetIndex
  receives data from MyStudySetStore
  render links to the Study Sets


## TestScore Cycle

# TestScores
  on mount, fetch users' test scores
  add listener to UserHistoryStore
  --> store
    --> emit change --> render


## Index Cycle
# Index
  on mount, fetch recent activities
  --> store
    --> emit change to Index


## New Study Set Form Cycle
# NewStudySetForm
  state: form content
  --> create new Study Set
    --> receive single study set --> store in WordStore
    --> redirect to the Study Set

## New Class Form Cycle
# NewClassForm
  state: form content
  --> create new Study Set
    --> receive single study set --> store in WordStore
    --> redirect to the Study Set



## Class Cycle
# Class

# StudySetIndex
  on mount, fetch all study sets of the class
  --> store
    --> emit change StudySetIndex receives the study sets
  add listener to StudySetIndexStore
  pass study sets as props to StudySetIndex

# StudySetIndexItem
  props: Study Set
  render link to the Study Set


## ProgressByStudySet Cycle
# ProgressByStudySet
  state: ProgressByStudySetStore.all()
  on mount, fetch all progress data of each study set
  add listener to ProgressByStudySetStore

  --> store
   -> emit change --> receive progress data --> pass to ProgressByStudySetItem as prop
# ProgressByStudySetItem
  props: progress data
  render prop data

## ProgressByStudent Cycle
# ProgressByStudent
  state: ProgressByStudentStore.all()
  on mount, fetch all progress data of each student
  add listener to ProgressByStudentStore

  --> store
   -> emit change --> receive progress data --> pass to ProgressByStudentItem as prop
# ProgressByStudentItem
  props: progress data
  render prop data


## StudySet Cycle
# Study Set
  state: words
  on mount, fetch all the words
  add listener to WordStore
  -->
# List
  receive words as props
  render list

# Flashcard
  receive words as props
  render each word


# Test
  receive words as props
  generate test


## Test Submission Cycle
# Test
  User submit their test
  --> create test record --> Store doesn't receive any new data
  --> Show a message upon successful submission with the test score
