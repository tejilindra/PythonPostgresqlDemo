This project is to demonstrate the Python application consuming twitter api to perform OAuth and python uses REST API, Flask and PostgreSQL to create user interactions on the client side.

**Prerequisites**: 
Python and PostgreSQL

**Installation steps:** 
1. Clone the project

**PostgresSQL:**
1. Run postgresql and login with the superuser password
2. Create a table in the postgreSQL db:
`CREATE TABLE users
(
	id SERIAL PRIMARY KEY,
	screen_name text,
	oauth_token text,
	oauth_token_secret text
)`
3. Update the database username and password in config.properties

**Get Twitter Consumer Secret Keys:**
1. Login to https://dev.twitter.com/apps/new and create a project. Click on key icon on the project and copy the API key and Secret from the View keys option:
2. Update Consumer key and secret with API key and secret respectively in the constants.py

**Python:**
1. Run pip install requirements in the terminal
2. Run app.py
3. Run localhost:4995 and Click "Log in with Twitter" link:
4. Navigates to Twitter Authorization App. Enter your password and click "Authorize App"
5. A successful twitter authorization will be generated with an Authorization code in this url: https://api.twitter.com/oauth/authorize
6. In another tab, update the authorization code in thi url and run: http://localhost:4995/auth/twitter?oauth_verifier=<authorization_code>
7. Run http://localhost:4995/profile will displayed with your logged in account and search box: 
8. A sample search on any keyword will display the results from the authorized twitter account.

**PostgresSQL Verification:**
1. SELECT * FROM public.users ORDER BY id ASC should display the recorded OAuth token and secret information stored in the PostgreSQL 
