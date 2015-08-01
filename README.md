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

##Tasks Implemented:
 
Task 1: Add Sessions to a Conference

Added the following endpoint methods:

createSession: given a conference, creates a session.

getConferenceSessions: given a conference, returns all sessions.

getConferenceSessionsByType: given a conference and session type, returns all applicable sessions.

getSessionsBySpeaker: given a speaker, returns all sessions across all conferences.

The following design choices where implemented for speaker model:

Property	| Type

name	    | string, required

highlights |	string

speaker	| string, required

duration	| integer

typeOfSession |	string, repeated

startDateTime |	DateTimeProperty

organizerUserId	|string



Task 2: Add Sessions to User Wishlist

Added an attribute sessionInWishlist in Profile model with a repeated key property filed.In order to interact with this model in API the following two endpoints were added:

1)addSessionToWishlist: Given a websafeSessionKey adds that session to user's wishlist.

2)getSessionsInWishlist:Returns all the sessions in the user's wishlist.

Task 3: Work on indexes and queries

Added the following two additional queries:

1)getUpcomingConferenceSessions: returns all upcoming session's in a particular conference.This would be really useful to the users to check the next coming sessions in a particular conference so that they can plan accordingly.

2)getConferencesByMonth: Given a month returns all the conferences starting in that month.

query related problem:Queries have only one  inequality filter, and it would cause a BadRequestError to filter on both startDate and typeOfSession.


Task 4: Add Featured Speaker

Made some changes to createSession endpoint to check if the speaker appeared in any other of the conference's sessions. If so, the speaker name and relevant session names were added to the memcache under the featured_speaker key. created the following endpoint:
1)getFeaturedSpeaker:check the memcache for the featured speaker. If empty, it would simply pull the next upcoming speaker.

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
