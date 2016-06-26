## React Components Hierarchy

* **App**
  * Navbar
  * Header with search
    * Index
    * **Class**
      * StudySetIndex
        * StudySetIndexItem
      * **ClassStudySets** (to see class's progress by study set, only if the user is the Teacher)
      * **Students** (to see class's progress by student, only if the user is the Teacher)
    * **StudySet**
      * StudySetDetail
      * **List**
      * **Flashcard**
      * **Test**
    * **SearchResults**


## Routes

Log-in/Sign-up routes
* /session
* /user

App
* Component: App, path /
  * Component: Index
  * Component: Class, path /class/:id
    * Component: ClassStudySets, path /class/:id/class_study_sets
    * Component: Students, path /class/:id/students
  * Component: StudySet, path /study_set/:id
    * Component: Flashcard, path /study_set/:id/flashcard
    * Component: List, path /study_set/:id/list
    * Component: Test, path /study_set/:id/test
  * Component: SearchResult, path/search
