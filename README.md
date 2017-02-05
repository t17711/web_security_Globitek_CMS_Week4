# Project 3 - Input/Output Sanitization

The input/output sanitization project is a two-week assignment. See Week 2 Assignment for full details.

- [x] Test for vulnerabilities
	* The xss test failed, returned cookie
	* sqli test failed, browser hanged, returned test failed
	* Csrf failed

- [x] Login page fixed
	* Error message added for failed login. Same message tor both user and password not forund to lower chance of dictionary attack
	* Added user ID on session data as user_id
	* Regenerate session ID after login

- [x] Restrict staff pages to people logged in
	* In initialize function, i made it so that for all pages that are in staff folder except login, we need to be logged in
	* If logged in date older than a day then, login invalid

- [x] Logout page
	* Added dsession unset and destroy functions on logout functions to destroy login data after logout.

- [x] Add CSRF protections to the state forms
	* Confirm that the referer sent in the requests is from the same domain as the host in staff/states/new.php and edit.php
	* Create and store CSRF token in sessions, and as hidden html input tag inside the form 
	* checked if csrf matched, if not skip reading post values

- [x] Did sqli prevention in login page

- [x] Bonus
	* There is security weakness in login page. It tells user if username or password is wrong. It helps dictionary attack.
	* csrf added tp all forms (new, edit) in staff directory.
	* csrf_token_time created and saved on session so that token older than 10 min is rejected.
	* Saved current http user agent to session during login.
	* Compared server user agent with seccion user agent during check login.
