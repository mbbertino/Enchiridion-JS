# Promises
Promises, sometimes also referred to as Deferreds and Futures, are objects whose value may or may not have been resolved, but whose value *will* be resolved (as either a success or failure). Rather than the usual nested asynchronous callbacks, promises can be used as a kind of placeholder object until the asynchronous action is complete. 

Promises have existed for a decades in other programming languages[^10], and now have, as of late 2013, native implementation in the latest Chrome and Firefox builds[^11].

An article on Parse's blog[^20] offers great examples:

The usual callback functions on a Parse object save method
```javascript
object.save({ key: value }, {
  success: function(object) {
    // the object was saved.
  },
  error: function(object, error) {
    // saving the object failed.
  }
});
```

The same effect using a promise and the `.then()` method on that promise
```javascript
object.save({ key: value }).then(
  function(object) {
    // the object was saved.
  },
  function(error) {
    // saving the object failed.
  })
```

This may seem like only a slight change in semantics, but the true beauty of JavaScript promises is that they are chainable. Rather than the difficult-to-reason-about nested callbacks (which most JavaScripters will have the misfortune to have written at some point in their careers), promises can be chained together for much cleaner implementation of the same flow. Again, two example from Parse's blog post:

Three nested callbacks
```javascript
Parse.User.logIn("user", "pass", {
  success: function(user) {
    query.find({
      success: function(results) {
        results[0].save({ key: value }, {
          success: function(result) {
            // the object was saved.
          }
        });
      }
    });
  }
});
```

…versus three chained promises.
```javascript
Parse.User.logIn("user", "pass").then(function(user) {
  return query.find();
}).then(function(results) {
  return results[0].save({ key: value });
}).then(function(result) {
  // the object was saved.
});
```

A number of libraries have made Promises available to JavaScript already, including jQuery[^30], and Kris Kowal's Q[^31] library. Be warned that promise libraries may not necessarily follow the official language spec.

## Resources

- [An Overview of JavaScript Promises](http://www.sitepoint.com/overview-javascript-promises)
- [A Deeper Dive Into JavaScript Promises](http://www.sitepoint.com/deeper-dive-javascript-promises/)
- [jQuery promises](http://api.jquery.com/promise/)



[^10]: According to [Wikipedia](http://en.wikipedia.org/wiki/Futures_and_promises#cite_note-1), Daniel P. Friedman, author of the classic [*The Little Schemer*](http://www.amazon.com/exec/obidos/ASIN/0262560992/wrrrldwideweb), first suggested "promise" as the term for this construct in 1976. Unfortunately, the aforementioned paper lives behind a paywall ($40 for an 8 page PDF), so we'll have to take Wikipedia's word for it. Foiled again!

[^11]: [An Overview of JavaScript Promises](http://www.sitepoint.com/overview-javascript-promises)

[^20]: [What's So Great About JavaScript Promises](http://blog.parse.com/2013/01/29/whats-so-great-about-javascript-promises/)

[^30]: jQuery's [.promise()](http://api.jquery.com/promise/)

[^31]: [Kris Kowal's Q library](https://github.com/kriskowal/q)
