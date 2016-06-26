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
      * List
      * **Flashcard**
      * **Test**


## Routes

Log-in/Sign-up routes
* /session
* /user

App
* Component: App, Path: /
  * Component: Content

    * Component: Dashboard
      * Component: Navbar
      * Component: Subcontent
        * Component: Index
        * Component: Class, Path: /class/:id
          * Component: StudySetIndex
          * Component: ClassStudySets, Path: /class/:id/class_study_sets
          * Component: Students, Path: /class/:id/students

        * Component: SearchResult, Path: /search_result

    * Component: StudySet, Path: /study_set/:id
      * Component: List
      * Component: Flashcard, Path: /study_set/:id/Flashcard
      * Component: Test, Path: /study_set/:id/test
