# FriendFinder

## Description

*Friend Finder* application is meant to simulate a simple dating app. The goal of this app is to bring in like-minded people together for fun, intimacy and love. Every day we’re finding new ways to help our members engage, communicate and connect with people who are looking for exciting experiences both online and offline. The application is implemented using a [Node.js](https://nodejs.org/en/) and [Express](https://expressjs.com/) server on the back end and the [Bootstrap](http://getbootstrap.com/) CSS framework on the front end.

*Friend Finder* implements friend matching based on the user's responses to a ten question survey. The user responds to questions with values from 1 (Strongly Disagree) to 5 (Strongly Agree). When the survey is submitted, an existing user record closest to the current user's responses is found and returned. The closest set of user responses is defined as the set with the lowest absolute difference for all ten questions combined.

## Live Link
 - https://tranquil-brook-54709.herokuapp.com/

## Technologies Used

- JavaScript
- jQuery
- node.js
- Express.js
- HTML
- Bootstrap

## Code Explanation
- Our `server.js` file sets up the Express server, specifying our port number, the npm packages that need to be loaded, and also the routes, which we have externalized
- There are 2 separate HTML files (`home.html` and `survey.html`) that serve as the front-end portion of our code; they determine what the user sees (the homepage and the survey, which will also show the resulting best match)
- Our 2 routing files (`htmlRoutes.js` and `apiRoutes.js`) determine the back-end logic (based on the request being made, the response that gets sent to the browser); the HTML routes display the survey and the homepage based on the URL that is accessed, and the API routes send back existing content in our server-side data or add new friends
- Best match is calculated by finding the friend with the minimal difference in scores and then sending that friend to the browser as a JSON object
- A modal is then toggled, displaying the the best match to the person who just took the survey
- In essense, this will also be a form of notes that you may later reference weeks later
- Friends are stored as such:

```js
{
  "name":"Ahmed",
  "photo":"https://media.licdn.com/mpr/mpr/shrinknp_400_400/p/6/005/064/1bd/3435aa3.jpg",
  "scores":[
      5,
      1,
      4,
      4,
      5,
      1,
      2,
      5,
      4,
      1
    ]
}
```
