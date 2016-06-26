## React Components Hierarchy

* **App**
  * Header
    * Search

  * Content
    * Dashboard
      * Navbar
        * MyClassesIndex
        * MyStudySetIndex
        * Footer
      * SubContent
        * Index
        * **StudySetForm**
        * **ClassForm**
        * **TestScores**
          * TestScoreItem
        * **Class**
          * StudySetIndex
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
      * Component: Subcontent
        * Component: Index
        * Component: StudySetForm, Path: /create_study_set (or edit_study_set/:id)
        * Component: ClassForm, Path: /create_class (or edit_class/:id)
        * Component: TestScores, Path: /test_scores
        * Component: Class, Path: /class/:id
          * Component: StudySetIndex
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
    [ ] Logo
    [ ] display user's username

  * Content
    * Dashboard
      * Navbar
        * MyClassesIndex
          [ ] links: classes the user created
          [ ] links: classes enrolled
          [ ] Link: create new study set form
        * MyStudySetIndex
          [ ] links: study sets the user created
          [ ] link: create new class form
        [ ] Link to TestScores
        * Footer
          [ ] dummy company info & links

      * SubContent
        * Index
          [ ] Recent activities by the users
        * StudySetForm
          [ ] page header changes (Create New/Edit)
          [ ] can add the set to classes
        * ClassForm
          [ ] page header changes (Create New/Edit)
          [ ] can add existing study sets
        * TestScores
          * TestScoreItem
            [ ] render test score and link to the study set
        * Class
          [ ] class title bannar
          [ ] Link to create new study set for the class (if current_user == teacher)
          [ ] Link to edit the class (if current_user == teacher)
          * StudySetIndex
            * StudySetIndexItem
              [ ] render link to the study set
          * ProgressByStudySet (only if the user is the Teacher)
            * ProgressByStudySetItem
              [ ] render data and link to the study set
          * ProgressByStudent (only if the user is the Teacher)
            * ProgressByStudentItem
              [ ] render <li>
        * SearchResults
          * SearchResultItem
            [ ] render link to the class/study set

    * StudySet
      [ ] Study Set title bannar
      [ ] Link to edit the study set (if current_user == creator)
      * List
      * Flashcard
      * Test
