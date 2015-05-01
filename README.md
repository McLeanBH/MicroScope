## APPLICATION MICROSCOPE

* Using Meteor.js and the "Discover Meteor" book, this app serves as a news feed similar to that of Reddit. Using meteor's internal server, running on local host with live-reload, but will deploy via Meteor CLI to web and iOS alike.






## NOTES:

* (from commit 8.3) - We’re taking the `fieldNames` array that contains a list of the fields being modified, and using Underscore’s `without()` Method to return a sub-array containing the fields that are not `url` or `title`. - (IMPLEMENT THIS IN edit_post.html) You might have noticed that nowhere in our post editing code do we check for duplicate links. This means a user could submit a link and then edit it to change its URL to bypass that check. The solution to this issue would be to also use a Meteor method for the edit post form, but we’ll leave this as an exercise to the reader.

* (on clearing errors and ridding the DOM of the `alerts`)
-- You’ll notice the error messages are disappearing by themselves after a few seconds. This works, but if you were to trigger multiple errors (by submitting the same link three times, for example) you’d notice that they’re getting stacked on top of one another. This is because while the .alert elements are disappearing visually, they’re still present in the DOM. We need to fix this. This is exactly the kind of situation where Meteor shines. Since the Errors collection is reactive, all we need to do to get rid of these old errors is remove them from the collection!
-- We’ll use Meteor.setTimeout to specify a callback function to be executed after the timeout (in this case, 3000 milliseconds) expires.
-- The rendered callback triggers once our template has been rendered in the browser. Inside the callback, this refers to the current template instance, and this.data lets us access the data of the object that is currently being rendered (in our case, an error).
