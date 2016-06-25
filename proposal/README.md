# (project name)

  Heroku Link

## Minimum Viable Product
(project name) is a web application inspired by Quizlet, a popular classroom tool for foreign language studies. On (project name) users are able to memorize new vocabularies in interactive ways, and teachers are able to track students' progress. The app will be built using Ruby on Rails and React.js.

I do not have 4 features listed as required, but I thought that types of features that I am considering might be adequate.

- [] Hosting on Heroku
- [] New account creation, log-in, and guest log-in
- [] Production README.md

- [] Study Sets (vocabulary lists)
  - [] Users can create new study sets
  - [] Each set includes the following features:
    - [] Flashcards
    - [] Test
  - [] The creator of the Study Set can edit and delete
  - [] Users can search for Study Sets created by other Users

- [] Test
  - [] Test is randomly generated based on the Study Set
  - [] When User submits Test, the score is recorded in DB
  - [] Users can see their past Test scores

- [] Classes
  - [] Users can create classes as Teacher
  - [] Users can search for Classes
  - [] Users request to join class as Students, and Teacher approves the request.
  - [] Teacher can add Study Sets to the class
  - [] Teachers can see Student's Test scores of the Study Sets that belong to the Class.

- [] Users
  - [] When logged-in, users see in Navbar:
    - [] Classes they created and/or enrolled
    - [] Study Sets they created
    - [] Study Sets they previously studied
  - [] When logged-out, users can:
    - [] search for classes and study sets
    - [] study Study Sets
    - [] not create new Study Sets
    - [] not enroll in classes
    - [] not record their Test scores


- [] Styling and Navigation
  - [] Adequate Styling that resembles Quizlet
  - [] Smooth, bug-free navigation
  - [] Users are warned when they navigate to invalid or deleted Study Set or Class
  - [] Adequate and appropriate seeds to demonstrate the feature

- [] Bonus
  - [] Users set their study sets as private
  - [] Search study sets, users, and classes
  - [] Game feature for study sets
  - [] Users select profile pictures

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
