# (project name)

  Heroku Link

## Minimum Viable Product
(project name) is a web application inspired by Quizlet, a popular classroom tool for foreign language studies. On (project name) students can memorize new vocabularies in interactive ways, and teachers can manage their classes. The app will be built using Ruby on Rails and React.js.

- [] Hosting on Heroku
- [] New account creation, log-in, and guest log-in
- [] Production README.md

- [] Study Sets (vocabulary lists)
  - [] Users can create, edit, and study sets
  - [] Users can search for Study Sets created by other Users
  - [] Each Study Set includes the following features:
    - [] List
      - [] display the list of all vocabulary pairs
    - [] Flashcards
      - [] show each vocabulary pair at a time
    - [] Test
      - [] Test is randomly generated based on the Study Set
      - [] When User submits Test, the score is recorded in DB
      - [] Users can see their past Test scores


- [] Classes
  - [] Users can create, edit, and delete classes as Teacher
  - [] Users can search for Classes
  - [] Only Teacher can add Study Sets to the Class
  - [] Teachers can see Student's Test scores.

- [] Users
  - [] When logged-in, users see in Navbar:
    - [] Classes they created and/or enrolled
    - [] Study Sets they created
    - [] Study Sets they previously studied
  - [] When logged-out, users can:
    - [] search for classes and study sets
    - [] use all Study Sets features
    - [] not create new Study Sets or Classes
    - [] not enroll in Classes
    - [] not record their Test scores


- [] Styling and Navigation
  - [] Adequate Styling that resembles Quizlet
  - [] Smooth, bug-free navigation
    - [] Users are informed when they navigate to invalid or deleted Study Set or Class
  - [] Adequate and appropriate seeds to demonstrate the feature


- [] Bonus
  - [] Users can customizable Test

  - [] Add more features to Study Sets
    - [] Users set their study sets as private
    - [] Study Set can handle non-Latin characters
    - [] Users can upload pictures that accompany words
    - [] Users can record correct pronunciation

  - [] Enrollment Request and Approval
    - [] Users request to enroll in Class as Students, and Teacher approves the request.
    - [] Show pending enroll request on Navbar (if the User is Teacher)

  - [] User Profile Page
    - [] Users have profile page
    - [] Users can add their info and share on their profile page
    - [] Users select profile pictures

  - [] Game feature for study sets
    - [] Interactive JavaScript game
    - [] When logged in, Users can share their score
    - [] Show highest scores

  - [] Folders
    - [] Users can create folders
    - [] Users can add their Study Sets to their folders
    - [] Users can add other users Study Sets to their folders




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
