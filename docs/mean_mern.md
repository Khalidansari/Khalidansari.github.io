# MEAN - MongoDB, Express, Angular, NodeJS (Replace Angular with ReactJS for MERN)

## How this all is tied together?

Frontend, which can act as an independent system, can be built on ReactJS or Vue, etc.

Backend, which can act as an independent system, is generally built using expressJS

Database, which can be any db. Can be connected simply by installing the db driver for that db using npm command and then configuring it.

## How will these independent apps coordinate with eachother?

If the site is public and does not need login mechanism then they can talk simply through REST api but if they are to be access after login then the following is the way:

1. Put a oauth/sso on the front

2. Frontend will always check if the session is valid before taking the request from the user. If it is valid then it will talk to backend for any data it needs else it will forward the user to the login page. SSO for this will have "Public" Access Type.

3. Backend will always take the bearer token along with any request from frontend. Then it will check with oauth/sso app to check if that is valid. If it is valid then it will send the backend data to frontend else it will throw some error. In case frontend receives the error, it needs to be able to make sense of it and if needed forward the user to login page. The access type for backend is "Bearer Only" because it will never by itself forward user to login page.
