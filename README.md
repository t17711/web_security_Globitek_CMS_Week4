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


## Video Walkthrough

Here's a walkthrough of implemented user stories:

<img src='https://github.com/t17711/web_security_Globitek_CMS_Week4/blob/master/walkthrough.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' /> *

GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while building the app.

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.