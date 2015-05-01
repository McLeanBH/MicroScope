## APPLICATION MICROSCOPE

* Using Meteor.js and the "Discover Meteor" book, this app serves as a news feed similar to that of Reddit. Using meteor's internal server, running on local host with live-reload, but will deploy via Meteor CLI to web and iOS alike.






## NOTES:

* (from commit 8.3) - We’re taking the `fieldNames` array that contains a list of the fields being modified, and using Underscore’s `without()` Method to return a sub-array containing the fields that are not `url` or `title`. - (IMPLEMENT THIS IN edit_post.html) You might have noticed that nowhere in our post editing code do we check for duplicate links. This means a user could submit a link and then edit it to change its URL to bypass that check. The solution to this issue would be to also use a Meteor method for the edit post form, but we’ll leave this as an exercise to the reader.
