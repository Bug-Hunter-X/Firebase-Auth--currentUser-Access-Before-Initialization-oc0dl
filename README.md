# Firebase Authentication: currentUser Access Before Initialization

This repository demonstrates a common error in Firebase Authentication where accessing the `currentUser` property before the authentication state is fully initialized can lead to unexpected errors.

The `bug.js` file showcases the problematic code, while `bugSolution.js` provides the corrected implementation.

## Problem
Attempting to access `firebase.auth().currentUser` prematurely before the Firebase authentication state is initialized results in null pointer exceptions and unexpected behavior.

## Solution
Use Firebase's `onAuthStateChanged` listener to ensure the authentication state is fully resolved before accessing `currentUser`.

This listener provides a callback function that executes when the authentication state changes, guaranteeing that `currentUser` will be properly initialized when accessed within the callback.