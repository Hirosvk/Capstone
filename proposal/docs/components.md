## React Components Hierarchy

* **App**
  * Header
    * Search

  * Content
    * Dashboard
      * Navbar
        * MyClassesIndex (only when logged-in: links to classes the user created/enrolled, form to create new study set)
        * MyStudySetIndex (only when logged-in: links to study sets the user created/studied, form to create new class)
        * Footer (dummy company info & links)
      * SubContent
        * Index
        * **Class**
          * StudySetIndex
            * StudySetIndexItem
          * **ClassStudySets** (to see class's progress by study set, only if the user is the Teacher)
          * **Students** (to see class's progress by student, only if the user is the Teacher)
        * **SearchResults**

    * **StudySet**
      * WordList
      * **Flashcard**
      * **Test**


## Routes

Log-in/Sign-up routes
* /session
* /user

App
* Component: App, Path: /
  * Component: Index
  * Component: Class, Path: /class/:id
    * Component: ClassStudySets, Path: /class/:id/class_study_sets
    * Component: Students, Path: /class/:id/students
  * Component: WordList, Path: /study_set/:id
    * Component: Flashcard, Path: /study_set/:id/Flashcard
    * Component: Test, Path: /study_set/:id/test
  * Component: SearchResult, Path: /search
