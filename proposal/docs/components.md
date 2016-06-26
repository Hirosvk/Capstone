## React Components Hierarchy

* **App**
  * Header
    * Search

  * Content
    * Dashboard
      * Navbar
        * MyClassesIndex (links to classes the user created/enrolled and form to create new study set)
        * MyStudySetIndex (links to study sets the user created/studied, form to create new class)
        * Footer (dummy company info & links)
      * SubContent
        * Index
        * **NewStudySetForm**
        * **NewClassForm**
        * **TestScores**
        * **Class**
          * StudySetIndex (include link to new study set if user is the teacher)
            * StudySetIndexItem
          * **ProgressByStudySet** (only if the user is the Teacher)
            * ProgressByStudySetItem
          * **ProgressByStudent** (only if the user is the Teacher)
            * ProgressByStudentItem
        * **SearchResults**
          * SearchResultItem

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
        * Component: NewStudySetForm, Path: /new_study_set
        * Component: NewClassForm, Path: /new_class
        * Component: TestScores, Path: /test_scores
        * Component: Class, Path: /class/:id
          * Component: StudySetIndex
            * Component: StudySetIndexItem
          * Component: ProgressByStudySet, Path: /class/:id/by_study_sets
            * Component: ProgressByStudySetItem
          * Component: ProgressByStudent, Path: /class/:id/by_students
            * Component: ProgressByStudentItem

        * Component: SearchResults, Path: /search_results
          * Component: SearchResultItem

    * Component: StudySet, Path: /study_set/:id
      * Component: List
      * Component: Flashcard, Path: /study_set/:id/Flashcard
      * Component: Test, Path: /study_set/:id/test


* **App**
  * Header
    * Search

  * Content
    * Dashboard
      * Navbar
        * MyClassesIndex
          [ ] links: classes the user created
          [ ] links: enrolled
          [ ] form to create new study set
        * MyStudySetIndex

         (links to study sets the user created/studied, form to create new class)
        * Footer (dummy company info & links)
      * SubContent
        * Index
        * **NewStudySetForm**
        * **NewClassForm**
        * **TestScores**
        * **Class**
          * StudySetIndex (include link to new study set if user is the teacher)
            * StudySetIndexItem
          * **ProgressByStudySet** (only if the user is the Teacher)
            * ProgressByStudySetItem
          * **ProgressByStudent** (only if the user is the Teacher)
            * ProgressByStudentItem
        * **SearchResults**
          * SearchResultItem

    * **StudySet**
      * List
      * **Flashcard**
      * **Test**
