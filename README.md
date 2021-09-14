![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

# Intro to CRUD and Firebase

| Timing | Type | Topic |
| --- | --- | --- |
| 10 min | [Opening](#opening) | Introduction to CRUD and Firebase |
| 10 min | [Review](#review) | A Little Review...A lotta CRUD |
| 10 min | [Introduction](#introduction1) | Understand CRUD Through Public APIs |
| 10 min | [Introduction](#introduction2) | Firebase Introduction |
| 15 min | [Setup](#setup) | Firebase Setup |
| 5 min | [Introduction](#introduction3)  | Intro to CRUD with Firebase |
| 20 min | [Codealong](#codealong1)  | Create with Firebase |
| 20 min | [Codealong](#codealong2) | Read wih Firebase  |
| 30 min | [Codealong](#codealong3) | Update with Firebase: Pairs  |
| 15 min | [Codealong](#codealong4) | Delete with Firebase: Pairs |
| 5 min |  [Conclusion](#conclusion)| Final Questions & Exit Tickets |


### Objectives

_After this lesson, students will be able to:_

- Explain what CRUD is.
- Explain the HTTP methods associated with CRUD.
- Implement Firebase in an application.
- Build a full-stack app.

### Preparation

_Before this lesson, students should already be able to:_

- Identify all the HTTP Verbs & their uses.
- Describe APIs & how to make calls and consume API data.

---

<a name = "opening"></a>
## Introduction to CRUD and Firebase (10 min)

In terms of an app's functionality, in general, most app's share the purpose of being able to show, create, update and delete data. For example, with Instagram a user is allowed to create and show data by uploading pictures with captions and share them with all their followers to see. Further, if the user wanted to go back and update the data, say they wanted to change the caption, they could do so by editing the caption or they could even delete all the data by removing the entire post. Similarly, with Tumblr, users can create posts they wish to share which they can edit later or even delete entirely. Being made aware of this pattern in apps can you name two or more apps and how they go about performing this functionality?

This common app functionality dealing with data is known as CRUD (Create, Read, Update and Delete). For today's lesson we will not only become familiar with this concept, but learn how to implement it with the help of a back-end service known as Firebase as we build out our very own CRUD application.

---

<a name = "review"></a>
## A Little Review...A Lotta CRUD (10 min)

Even though we have never explicitly covered the term CRUD in this course, we have covered some of the technical implementations of performing CRUD. Can you think of what we have learned in an earlier lesson that relates to an application's ability to create, read, update and delete data? If it is not apparent as of yet, take a step back to think about what we know is needed in order to "play" with data. If the term API comes to mind you're on the right track.

When developing an application that deals with data, a developer must be able to communicate with the application program interface (API) using various HTTP methods. To better understand how the different HTTP methods we already know perform CRUD checkout at the following table:

|HTTP Method|CRUD|Further explanation|
|:---|:-----|:-----|
|POST| Create|Most-often utilized to _create_ new resources. On successful creation returns a 201 status code.
|GET| Read|The HTTP GET method is used to _read_ a representation of a resource. Upon success, returns data in the form of XML or JSON with a 200 status code. Upon failure, often returns a 404 or 400.
|PUT| Update|Most often utilized to for _update_ capabilities. Upon successful update, often returns a 200 or 204.
|DELETE| Delete|Used to _delete_ a resources. Upon successful deletion, most often returns a 200 status code.

---

<a name = "introduction1"></a>
## Understand CRUD Through Public APIs (10 min)

Now that you have an understanding of what CRUD is and how HTTP methods help you implement it, we can take a look at the following APIs to see what HTTP methods a developer must use to perform at least one instance of create, read, update and destroy. Further, you must define what exactly is being created, read, updated or deleted.

API options:

- Facebook
- Instagram
- Twitter
- YouTube
- Flickr

> **Note:** Certain APIs may not allow for full CRUD functionality. If you're researching one of these APIs be sure to point out its limitations.

---

<a name = "introduction2"></a>
## Firebase, a Back-end Service (10 min)

So far in this course we have covered how to consume data from third-party APIs, but have not yet created our own API. The work that we have been doing is what is known in the tech industry as client-side or _front-end_ development.

> Front end development, also known as client side development is the practice of producing HTML, CSS and JavaScript for a website or web application so that a user can see and interact with them directly.

> -Wikipedia

The process of actually creating the API, not consuming it, is what is known as _back-end_ development. You can think of back-end code as all the code living on the server-side, the code that app users never interact with directly. It is the "non-HTML-CSS-JavaScript" code.

Even though we don't have all the skills needed to roll out our own fully custom back-end, today we are going to learn how to use Firebase, a back-end as a service (BEaaS), to help us create our very own API!

Firebase serves as the entire back-end of an application, meaning its biggest features include working as a database for your app as well as providing you with a Javascript library to interact with said database. It's truly a great tool for designers/front-end developers that are either not familiar or don’t want to deal with building out the back-end. Sometimes you just want to quickly prototype and focus on your UX! Some noteworthy users of Firebase include CBS, Instacart and Jawbone. And in terms of cost, each app is allowed to have a database with 100 users connected simultaneously for free!

So, without further ado, let's go ahead and get setup an application with Firebase!

---
<a name = "setup"></a>

## Firebase Setup (15 min)

Firebase is a Google product.

1. Go to https://console.firebase.google.com and click add a project.
2. Give your project a name. Something descriptive of what you are building would be nice. Today we are building a Message site. You don't need Google Analytics for today's project but perhaps for a real one you would.
3. Click the Web icon (looks like: `</>`)
4. Register your app. Yes, you need both an app and a project name. They can be the same. You don't need hosting.
5. Copy and paste the configuration they show you somewhere safe. We'll need that later to connect.
6. Click Cloud Firestore then create database.
7. Start in test mode for now, then choose a region near you for the location. Click enable.
8. Click Start Collection. Let's name this "messages". It'll ask you to define the first item for your data. We want the id to be auto-generated. Add a `message` property that is a string and `votes` property that is a number. Put in whatever message you want and `0` for `votes`. Click save.
9. We are ready to roll.

---

## Frontend Code Along

Take a look at [starter-code/firebase](starter-code/firebase). Those are the files we'll start with.

We'll move forward and try to accomplish the following:
1. Add the ability to render currently existing messages (the ones you created in setup above).
2. Add the ability to add a new message with the HTML form then call what implemented in 1 so that the list of messages displays the newly created message.
3. Add update functionality to add a vote or subtract a vote from a specific message. That will also be followed by re-rendering the list of messages with the latest.
4. Add delete functionality. The ability to delete a message and re-render the list.

<a name = "introduction3"></a>
## Intro to CRUD with Firebase (5 min)

Now that you are familiar with Firebase and how to set it up as a back-end for your application, we are going to cover how to properly implement CRUD functionality with it. Further, we will learn by doing! Once again, I'll first explain how to implement a new technical concept while you watch, and then when I'm done you and a teammate will go ahead and apply your new knowledge. Team up with a partner and for the next five minutes try to think of a simple app you'd like to build that implements CRUD. Your app must be able to Create, Read, Update and Delete data. This can be anything from a to-do list to a blog! Once you have your idea in mind go ahead and use the dashboard to create your new app. After you've done so go ahead and get your appropriate URL key to initialize your app and initialize your Firebase app utilizing the starter code.

---

<a name = "codealong1"></a>
## Create with Firebase (15 min)

The first part of CRUD we'll be covering is _C_, create.

We'll start with [these files](starter-code/firebase).

```js
  // Initialize Firebase
  const firebaseConfig = {
    apiKey: 'YOUR KEY',
    authDomain: 'YOUR INFO',
    projectId: 'YOUR INFO',
    storageBucket: 'YOUR INFO',
    messagingSenderId: 'YOUR INFO',
    appId: 'YOUR INFO',
  };

  firebase.initializeApp(firebaseConfig);

  const db = firebase.firestore();
  
  // Place in onLoadHandler()
  document.getElementById('message-form').addEventListener('submit', (event) => {
    // by default a form submit reloads the DOM which will subsequently reload all our JS
    // to avoid this we preventDefault()
    event.preventDefault();

    const messageInput = document.getElementById('newmessage');

    db.collection("messages").add({
      message: messageInput.value,
      votes: 0
    }).then(() => {
      messageInput.value = '';
    });

  });
```

Thinking on a high-level, in order to gather data from a user we must supply them with something in the view. What could that be? Yup, a form. I won't show you the HTML that goes with this script, because by this point you should be able to somewhat visualize it by reading the code, but if you are really struggling to comprehend what HTML is associated with this script you can refer to the solution code.

Looking at the code we can see that its purpose is primarily to capture the message input supplied by user upon submit of the `#message-form` form. Once this fan message is obtained we can go ahead and start to use Firebase to save the message and _create_ the data.

Firebase uses the JSON format for data--you'll recall that JSON data consists of key/value pairs, just like JavaScript objects. In this case, the key is `message` and its value is the message input value grabbed from the DOM. Further, we can also set `votes` values for each entry in the database. Since we know that the message hasn't been made public yet, and therefore hasn't received any votes, we can initialize its value to `0`.

Another important thing to note is that Firebase plays heavily on URLs. Besides checking your Dashboard you can also find data by using Firebase's structured URL format for querying, `https://firestore.googleapis.com/v1/projects/<project id>/databases/(default)/documents/<key of db key>`. For example, `https://firestore.googleapis.com/v1/projects/korn-fan-site/databases/(default)/documents/messages`.

The ability to access data by using a structured URL request is essentially calling upon the Firebase API which we have custom created by dynamically creating data. This will come into play as we seek to update specific pieces of data later in this lesson.

Once the functionality is fully implemented and used by a user, we have covered the _C_ in CRUD. Do you remember which HTTP method goes along with Create?

---

<a name = "codealong2"></a>
## Read with Firebase (20 min)

After a message has been successfully saved to our database in the back-end, we want to be able to show (_Read_) it on our app for the world to see. In order to do this we are going to need to follow a few steps:

- create a function that queries our database for fan message data
- call the function upon the initialization of the app
- bind the queried data to the DOM for users to see

So, how do we go about the first step, querying our Firebase database?

```js
const getFanMessages = async () => {
  const data = await db.collection('messages').get();

  // transform to a more useful format
  const messages = data.docs.map((doc) => {
    // below combines the document id with all properties returned by doc.data()
    return {
      id: doc.id,
      ...doc.data()
    };
  });

  return messages;
};
```

Now it is up to you to implement all three steps listed above to create the _read_ functionality of your app. Now lets show your app users some data!

```js
const listContainer = document.getElementById('message-container');
const messages = await getFanMessages();
listContainer.innerHTML = '';

messages.forEach((messageItem) => {
  listContainer.innerHTML += `<td>${messageItem.message}</td>`;
});
```

For your final project, you might want to filter the results returned with a query. Click the inverted pyramid in the Firestore console and form your query. It will generate the code for you! 

[](images/firestore-query.png)

For example:
```js
// get only messages where votes are greater than 0. Sort by votes ascending.
db.collection("messages")
  .where("votes", ">", 0)
  .orderBy("votes", "asc")
```
---

<a name = "codealong3"></a>
## Update with Firebase (30 min)

Lets pair up and work together on Update and Delete. Continue to follow along with the tutorial and implement functionality of the other buttons.

Some tasks to keep in mind:
* When populating rows of data, make sure to include thumbs up/down and trash buttons
* Vote functionality with the thumbs up/down buttons
* Delete functionality with the trash button

It get's simpler if you want to decrement or increment a value on your update call. In that scenario, there's no need to know what the current value is...you can just tell it to increment or decrement the current value! Here is how it's done:

```js
// increment
db.collection('messages').doc(id).update({
  votes: firebase.firestore.FieldValue.increment(1)
});

// decrement
db.collection('messages').doc(id).update({
  votes: firebase.firestore.FieldValue.increment(-1)
});
```
>Note: Remember when we did Read and got the `messages` back, there was also an `id` field

To perform the _U_ in CRUD, follow these simple steps:

- find the data you wish to update
- update its value with the new value
- save

Note that in Firebase, `update()` will update only the specific fields for which you pass in new values, while `set()` will overwrite all of the fields with new values.

<details close>
<summary>Firebase's REST API</summary>
<br>
Up until this point, we have not been concerned with specific <code>message</code> data. We have either created a new JSON object or retrieved all data objects at once. However, for <code>update</code>, we are concerned with updating specific messages, so the question arises, how will we be able to identify and retrieve a specific piece of data? Well, Firebase makes this task of data access fairly easy by creating an API for us that is based off the structure of our data objects. Can you remember Firebase's data URL structure we covered a little earlier? In case you forgot it's: <code>https://firestore.googleapis.com/v1/projects/{project id}/databases/(default)/documents/{collection name}</code>.
<br>

More on [Firebase's REST API](https://firebase.google.com/docs/firestore/use-rest-api)

Looking at the code above, you can see how we utilize this URL to access the specific `message` data we want and set a reference to it. Then, with our reference we can use the `update` method to redefine certain key values of our `message`'s data object, in this case votes. It's as simple as that!

Go ahead and take this knowledge to incorporate _update_ functionality within your app.
</details>

---

<a name = "codealong4"></a>
## Delete with Firebase (15 min)

```js
function deleteMessage(id) {
  // find message whose objectId is equal to the id we're searching with
  return db.collection('messages').doc(id).delete();
}
```

To perform the _D_ in CRUD:

- find the data you wish to delete
- use the `.delete()` method upon the data to delete it

_Delete_ is very similar to _update_ in that you must query for the specific piece of data you wish to delete. However, instead of updating column data you merely use the `remove` method upon your returned data to remove it from the database.

Finish off the amazing CRUD-ness of your app by implementing this freshly learned _delete_ functionality!

---

<a name = "conclusion"></a>
## Conclusion (5 min)

- What does CRUD stand for?
- What HTTP methods are associated with C, R, U and D?
- What is a BEaaS?
- Why would some developers choose to use the Firebase service?
- Is Firebase free?
- Do all apps have CRUD?
- How would you explain the front-end vs. the back-end to a fellow developer?

### Resources

* [Firebase's REST API](https://firebase.google.com/docs/firestore/use-rest-api)
