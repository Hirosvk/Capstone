## React Components Hierarchy

* **App**
  * Header
    * Search

  * Content
    * Dashboard
      * Navbar
        * MyCreatedClassesIndex
        * MyEnrolledClassesIndex
        * MyStudySetIndex
        * Footer
      * SubContent
        * Index
        * **StudySetForm**
        * **ClassForm**
        * **TestScores**
          * TestScoreItem
        * **Class**
          * ClassStudySetIndex
            * ClassStudySetIndexItem
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
        * Component: StudySetForm, Path: /create_study_set (or edit_study_set/:id)
        * Component: ClassForm, Path: /create_class (or edit_class/:id)
        * Component: TestScores, Path: /test_scores
        * Component: Class, Path: /class/:id
          * Component: ClassStudySetIndex
          * Component: ProgressByStudySet, Path: /class/:id/by_study_sets
          * Component: ProgressByStudent, Path: /class/:id/by_students

        * Component: SearchResults, Path: /search_results

    * Component: StudySet, Path: /study_set/:id
      * Component: List
      * Component: Flashcard, Path: /study_set/:id/Flashcard
      * Component: Test, Path: /study_set/:id/test


## Contents
* App
  * Header
    * Search
    - [ ] Logo
    - [ ] display user's username

  * Content
    * Dashboard
      * Navbar
        * MyCratedClassesIndex
          - [ ] links: classes the user created
          - [ ] Link: create new study set form
        * MyEnrolledClassesIndex
          - [ ] links: classes enrolled
        * MyStudySetIndex
          - [ ] links: study sets the user created
          - [ ] link: create new class form
        - [ ] Link to TestScores
        * Footer
          - [ ] dummy company info & links

      * SubContent
        * Index
          - [ ] Welcome message and navigation tips
        * StudySetForm
          - [ ] page header changes based on hashHistory (Create New/Edit)
          - [ ] delete button
          - [ ] can add the set to classes
        * ClassForm
          - [ ] page header changes based on hashHistory (Create New/Edit)
          - [ ] delete button
          - [ ] can add existing study sets
        * TestScores
          * TestScoreItem
            - [ ] render test score and link to the study set
        * Class
          - [ ] class title banner
          - [ ] Link to create new study set for the class (if current_user == teacher)
          - [ ] Link to edit the class (if current_user == teacher)
          * ClassStudySetIndex
            * ClassStudySetIndexItem
              - [ ] render link to the study set
          * ProgressByStudySet (only if the user is the Teacher)
            * ProgressByStudySetItem
              - [ ] render data and link to the study set
          * ProgressByStudent (only if the user is the Teacher)
            * ProgressByStudentItem
              - [ ] render <li>
        * SearchResults
          * SearchResultItem
            - [ ] render link to the class/study set

    * StudySet
      - [ ] Study Set title banner
      - [ ] Link to edit the study set (if current_user == creator)
      - [ ] does not show Navbar (original Quizlet is designed this way)
      - [ ] Back to Index link
      * List
      * Flashcard
      * Test
