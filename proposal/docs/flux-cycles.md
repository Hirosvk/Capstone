# Stores
* SearchResultStore
* NavbarStore
* ClassStudySetStore
* ProgressByStudySetStore
* ProgressByStudentStore
* StudySetStore
* TestScoreStore


# Actions
* UserAction
 * fetchNavbarRecords
 * receiveNavbarRecords
 * fetchTestScore
 * receiveTestScore

* ClassAction
  * fetchStudySets
  * receiveStudySets
  * fetchProgressByStudySet
  * receiveProgresByStudySet
  * fetchProgressByStudent
  * receiveProgressByStudent
  * toggleEnrollment
    - [ ] calls fetchStudySets
    - [ ] calls UserAction.fetchNavbarRecords
  * createNewClass
    - [ ] pass callback from View, which display the status of the request
    - [ ] calls fetchStudySets
    - [ ] calls UserAction.fetchNavbarRecords


* StudySetAction
  * fetchStudySet
  * receiveStudySet
  * createNewStudySet
    - [ ] pass callback from View, which display the status of the request
    - [ ] calls fetchStudySet
    - [ ] calls UserAction.fetchNavbarRecords


* TestAction
  * submitTest
    - [ ] pass callback from View, which display the status of the request
    - [ ] no receive action

* SearchAction
  * querySearchText
  * receiveSearchResults


# Flux Cycles

## Search Cycle
  * user enter search text and submit
  * SearchAction.querySearchText
  * SearchAction.receiveSearchResult
  * SearchResultStore receive the new data
  * SearchResults receive the new data, pass it to SearchResultItem

### Search
  * state: searchText
  * listens for search submit

### SearchResults
  * state: searchResults
  * componentDidMount:
    * add listener to SearchResultStore
      * callback: setState with new SearchResults
  * pass each result item as prop to SearchResultItem

### SearchResultItem
  * props: result item
  * render link to class/study Set



## Navbar Cycle
  * Navbar mounts
  * UserAction.fetchNavbarRecords
  * UserAction.receiveNavbarRecords
  * NavbarStore receives new data
  * Navbar view setState with new data

  * when user create/edit study sets or classes, or enroll in new class, it calls UserAction.fetchNavbarRecords

### Navbar
  * state: NavbarStore.all()
  * componentDidMount:
    * call UserAtion.fetchNavbarRecords
    * addListener to NavbarStore
      * setState to the new data
  * pass state to its children as props

### MyCreatedClassesIndex
  * prop: classes
  * receiveNewProps:
    * set new props as instance variable
  * render links to the classes

### MyCreatedClassesIndex
  * prop: classes
  * receiveNewProps:
    * set new props as instance variable
  * render links to the classes

### MyStudySetIndex
  * prop: study sets
  * receiveNewProps:
    * set new props as instance variable
  * render links to the study sets




## Study Set Form Cycle
  * StudySetAction.createNewStudySet
  * on success
    * StudySetAction.fetchStudySet & UserAction.fetchNavbarRecord --> see Navbar Cycle
    * StudySetStore receives new data
    * StudySetForm redirect to the Study Set page
  * on error
    * user receive error messages
    * user stays on the same page

### StudySetForm
  * state: form content

  * componentDidMount:
    * addListener to StudySetStore
      * callback: redirect to the created page
  * when calling StudySetAction.createNewStudySet
    * successCallback: StudyAction.fetchStudySet
    * errorCalback: display error message


## Class Form Cycle
  * ClassAction.createNewClass
  * upon success
    * ClassAction.fetchClass & UserAction.fetchNavbarRecord --> see Navbar Cycle
    * ClassStudySetStore receives new data
    * ClassForm redirect to the ClassIndex page
  * upon error
    * user receive error messages
    * user stays on the same page

### ClassForm
  * state: form content
  * componentDidMount:
    * addListener to ClassStudySetsStore
      * callback: redirect to the created page
  * when calling ClassAction.createNewClass
    * successCallback: ClassAction.fetchClassStudySets
    * errorCalback: display error message



## StudySet Cycle
  * StudySet mounts
  * StudySetAction.fetchStudySets
  * StudySetStore receives data
  * StudySet receives the new data

### StudySet
  * state:
    * Study Set info
    * words
  * componentDidMount:
    * StudySetAction.fetchStudySets
    * Add Lister to StudySetStore
      * callback: setState
  * pass state.words to children as props
### List
  receive words as props
  render list

## Test
  receive words as props
  generate test


### Test Submission Cycle
  * Test submit
    * Test.gradeTest
      * Test.showScore
      * TestAction.submitTest (no Dispatcher action)
        * callback: alert the request status
## Test
  * componentDidMount:
    * add event listener to test form on submit
  * pass callback to TestAction.submitTest




## Class Cycles
  * ClassStudySetIndex mounts
  * ClassAction.fetchStudySets
  * ClassAction.receiveStudySets
  * ClassStudySetStore receives data
  * StudySetIndex rest its state

### StudySetIndex
  * componentDidMount:
    * add listener to ClassStudyStore
      * setState
    * ClassAction.fetchStudySets
  * pass study sets as props to StudySetIndexItem

### StudySetIndexItem
  props: StudySet item
  render link to the Study Set


## ProgressByStudet Cycles

## ProgressByStudySet Cycle
  * same flow as ClassStudySet Cycle

## ProgressByStudent Cycle
  * same flow as ClassStudySet Cycle


## TestScore Cycle

### TestScores
  * state: TestScoreStore.all()
  * componentDidMount:
    * UserActon.fetchTestScores
    * addListener to TestScoreStore
      * callback: setState with new TestScoreStore.all()
