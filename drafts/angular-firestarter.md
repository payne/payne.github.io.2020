---
title: "Angular FireStarter -- great way to write angular program that uses FireBase.com."
date: "2018-12-26"
template: "post"
draft: false
slug: "/posts/angular-firestarter/"
tags:
  - "JavaScript"
  - "tools"
category: JavaScript 
description: "Angular FireStarter is great!"
---

## Start the project 

1. `git clone https://github.com/codediodeio/angular-firestarter.git f2`
2. `cd f2`
3. `time npm install` # takes 13 minutes & 36 seconds on my computer 
4. `vim src/environments/environments.ts`
5. `cd functions/;npm install --save firebase-functions@latest`

## Provision the project on Firebase.com

1. https://console.firebase.google.com/
2. Click + near the middle of the screen to add a new project.
3. I'll name this one matt-f2 --- name yours whatever you like.
4. Check the accept the controller-controller terms
5. Click Create project
6. Click continue and go to your project's URL -- Mine is https://console.firebase.google.com/project/matt-f2/overview 
7. Click the </> icon for web configuration.  
8. Copy the config object.  You'll copy these values to the envrionment.ts files of the project (there are two of them).
9. https://console.firebase.google.com/project/matt-f2/authentication/users and setup google authentication.
10. https://console.firebase.google.com/project/matt-f2/database create cloud firestore database with rules in test mode.

## Try it locally

1. cd to the main root
2. `ng serve`
3. http://localhost:4200
4. Click login and use your google account
5. Click firestore the upper right -- add a few notes
6. Navigate from firestore.com project's database  -- see that you've added a few records to the NoSQL datastore

## Try it on firebase.com's hosting service

1. `npm install -g firebase-tools`  # this is a one time setup
2. `firebase login` # You're prompted via your web browser
3. `firebase list` # lists your firebase projects
4. `firebase use matt-f2` # whatever project you are using
5. `time ng build` # takes 28 seconds on my computer
6. `time firebase deploy`# takes 2 minutes & 7 seconds on my computer
7. Visit https://matt-f2.firebaseapp.com login, make some notes, be happy.
8. Improve the cloud firestore rules by requiring authenticated users:

```javascript
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read: if request.auth.uid != null;
      allow write: if request.auth.uid != null;
    }
  }
}
```


# Note

1. The commit history of this work might interest you: https://github.com/payne/f2/commits/master 


