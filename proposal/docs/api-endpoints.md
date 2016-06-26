# html API
## Root
* GET /
  * static_page loads React App

## user
* GET /users/new
  * sign-in page
* POST /users
  * create new user

## session
* GET /session/new
  * log-in page
* POST /session/
  * log-in
  * redirects to GET /
* DELETE /session/
  * log-out
  * redirects to /session/new

# JSON API
