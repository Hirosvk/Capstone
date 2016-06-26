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
        * **NewStudySetForm**
        * **NewClassForm**
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
        * Component: NewStudySetForm, Path: /create_study_set
        * Component: NewClassForm, Path: /create_class
        * Component: TestScores, Path: /test_scores
        * Component: Class, Path: /class/:id
          * Component: ClassStudySetIndex
          * Component: ProgressByStudySet, Path: /class/:id/by_study_sets
          * Component: ProgressByStudent, Path: /class/:id/by_students

        * Component: SearchResults, Path: /search_results

    * Component: StudySet, Path: /study_set/:id
      * Component: List
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
        * MyCreatedClassesIndex
          - [ ] links: classes the user created
          - [ ] Link: NewClassForm
        * MyEnrolledClassesIndex
          - [ ] links: classes enrolled
        * MyStudySetIndex
          - [ ] links: study sets the user created
          - [ ] link: NewStudySetForm
        - [ ] Link to TestScores
        * Footer
          - [ ] dummy company info & links

      * SubContent
        * Index
          - [ ] Welcome message and navigation tips
        * NewStudySetForm
          - [ ] delete button
          - [ ] can add the set to classes
        * NewClassForm
          - [ ] delete button
          - [ ] can add existing study sets
        * TestScores
          * TestScoreItem
            - [ ] render test score and link to the study set
        * Class
          - [ ] class title banner
          - [ ] Link to create new study set for the class (if current_user == teacher)
          - [ ] toggle button to enroll in the class (if user is not the student or teacher)
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
      - [ ] does not show Navbar (original Quizlet is designed this way)
      - [ ] Back to Index link
      * List
      * Test
