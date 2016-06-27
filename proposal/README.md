# (project name)

  Heroku Link

## Minimum Viable Product
(project name) is a web application inspired by Quizlet, a popular classroom tool for foreign language studies. On (project name) students can memorize new vocabularies in interactive ways, and teachers can manage their classes. The app will be built using Ruby on Rails and React.js.

- [ ] Hosting on Heroku
- [ ] New account creation, log-in, and guest log-in
- [ ] Production README.md

- [ ] Study Sets (vocabulary lists)
  - [ ] Users can create, and delete study sets
  - [ ] Users can search for Study Sets created by other Users
  - [ ] Each Study Set includes the following features:
    - [ ] List
      - [ ] display the list of all vocabulary pair
    - [ ] Test
      - [ ] Test is randomly generated based on the Study Set
      - [ ] When User submits Test, the score is recorded in DB
      - [ ] Users can see their past Test scores


- [ ] Classes
  - [ ] Users can create and delete classes as Teacher
  - [ ] Users can search for Classes
  - [ ] Only Teacher can add Study Sets to the Class
  - [ ] Teachers can see Student's Test scores.

- [ ] Users
  - [ ] When logged-in, users see in Navbar:
    - [ ] Classes they created and/or enrolled
    - [ ] Study Sets they created
    - [ ] Study Sets they previously studied
  - [ ] When logged-out, users can:
    - [ ] search for classes and study sets
    - [ ] use all Study Sets features
    - [ ] not create new Study Sets or Classes
    - [ ] not enroll in Classes
    - [ ] not save their Test scores or study history


- [ ] Styling and Navigation
  - [ ] Adequate Styling that resembles Quizlet
  - [ ] Smooth, bug-free navigation
    - [ ] Users are informed when they navigate to invalid or deleted Study Set or Class
    - [ ] Users are informed when their navigation is unauthorized
  - [ ] Adequate and appropriate seeds to demonstrate the feature


- [ ] **Bonus**
  - [ ] Users can edit their classes
  - [ ] Users can edit their study sets
  - [ ] Flashcard feature for Study Sets
  - [ ] Add language tags to Study Sets and Class belong
    - [ ] users can choose one language to tag the study set/class when creating/editing
  - [ ] App tracks which Study Sets the user has studied
    - [ ] logged-in users can see Recently Studied Sets

- [ ] **Super Bonus**
  - [ ] Users can customizable Test

  - [ ] Recent Activities page

  - [ ] Add more features to Study Sets
    - [ ] Users set their study sets as private
    - [ ] Study Set can handle non-Latin characters
    - [ ] Users can upload pictures that accompany words
    - [ ] Users can record correct pronunciation

  - [ ] Enrollment Request and Approval
    - [ ] Users request to enroll in Class as Students, and Teacher approves the request.
    - [ ] Show pending enroll request on Navbar (if the User is Teacher)

  - [ ] Game feature for study sets
    - [ ] Interactive JavaScript game
    - [ ] When logged in, Users can share their score
    - [ ] Show highest scores

  - [ ] User Profile Page
    - [ ] Users have profile page
    - [ ] Users can add their info and share on their profile page
    - [ ] Users select profile pictures





## Design Docs
  * [View Wireframes][views]
  * [React Components][components]
  * [Flux Cycles][flux-cycles]
  * [API endpoints][api-endpoints]
  * [DB SChema][schema]

[views]: docs/views.md
[components]: docs/components.md
[flux-cycles]: docs/flux-cycles.md
[api-endpoints]: docs/api-endpoints.md
[schema]: docs/schema.md

## Implementation Timeline
