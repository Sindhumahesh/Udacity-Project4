Conference Central App
##Description
- 


- 
## Products
- [App Engine][1]

## Language
- [Python][2]

## APIs
- [Google Cloud Endpoints][3]
 
Task 1: Add Sessions to a Conference

Added the following endpoint methods:

createSession: given a conference, creates a session.
getConferenceSessions: given a conference, returns all sessions.
getConferenceSessionsByType: given a conference and session type, returns all applicable sessions.
getSessionsBySpeaker: given a speaker, returns all sessions across all conferences.

For the Speaker model design, I implemented the following datastore properties:


ask 2: Add Sessions to User Wishlist

Overview

Users should be able to mark some sessions that they are interested in and retrieve their own current wishlist. You are free to design the way this wishlist is stored.
Define the following Endpoints methods
addSessionToWishlist(SessionKey) -- adds the session to the user's list of sessions they are interested in attending

You can decide if they can only add conference they have registered to attend or if the wishlist is open to all conferences.
getSessionsInWishlist() -- query for all the sessions in a conference that the user is interested in


## Setup Instructions
1. Update the value of `application` in `app.yaml` to the app ID you
   have registered in the App Engine admin console and would like to use to host
   your instance of this sample.
1. Update the values at the top of `settings.py` to
   reflect the respective client IDs you have registered in the
   [Developer Console][4].
1. Update the value of CLIENT_ID in `static/js/app.js` to the Web client ID
1. (Optional) Mark the configuration files as unchanged as follows:
   `$ git update-index --assume-unchanged app.yaml settings.py static/js/app.js`
1. Run the app with the devserver using `dev_appserver.py DIR`, and ensure it's running by visiting
   your local server's address (by default [localhost:8080][5].)
1. Generate your client library(ies) with [the endpoints tool][6].
1. Deploy your application.


[1]: https://developers.google.com/appengine
[2]: http://python.org
[3]: https://developers.google.com/appengine/docs/python/endpoints/
[4]: https://console.developers.google.com/
[5]: https://localhost:8080/
[6]: https://developers.google.com/appengine/docs/python/endpoints/endpoints_tool
