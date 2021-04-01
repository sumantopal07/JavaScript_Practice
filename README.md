### REST API PRACTICE 
  https://github.com/sumantopal07/Rest-API-Intermediate-Hackerrank-Test
### PROMISES
  http://csbin.io/promises

> CHALLENGE 1: Using setTimeout, print the string 'Hello!' after 1000ms.

```js
function sayHello() {
    setTimeout(() => {
        console.log("hello");
    }, 1000);
}

console.log("hi");
sayHello();
```

> CHALLENGE 2:Create a promise. Have it resolve with a value of 'Resolved!' in resolve after a delay of 1000ms, using setTimeout. Print the contents of the promise after it has been resolved by passing console.log to .then

```js
var promise = new Promise(function (resolve, reject) {
    setTimeout(resolve, 1000);
});

promise.then(() => {
    console.log("Resolved!");
})
```

> CHALLENGE 3: Create another promise. Now have it reject with a value of "Rejected!" without using setTimeout. Print the contents of the promise after it has been rejected by passing console.log to .catch

```js
var promise = new Promise(function (resolve, reject) {
    reject();
})
promise.catch(() => {
    console.log("Reject!");
})
```

> CHALLENGE 4: Promises are asynchronous and we're now going to prove that they indeed are! Create a promise and have it resolve with the value of "Promise has been resolved!" Then uncomment the code at bottom of Challenge 4. What order do we expect "Promise has been resolved!" and "I'm not the promise!" to print? Why?

```js
var promise = new Promise(function (resolve, reject) {
    resolve();
});

promise.then(() => console.log('Promise has been resolved!'));
console.log("I'm not the promise!");
```

> CHALLENGE 5: Write a function delay that returns a promise. And that promise should return a setTimeout that calls resolve after 1000ms

```js
function delay() {
    return new Promise(function (resolve, reject) {
        resolve();
    });
}
function sayHello() {
    setTimeout(() => {
        console.log("hello");
    }, 1000);
}
delay().then(sayHello);
```

> CHALLENGE 6: This challenge we'll chain promises together using ".then" Create two variables: firstPromise and secondPromise Set secondPromise to be a promise that resolves to "Second!" Set firstPromise to be a promise that resolves to secondPromise Call the firstPromise with a ".then", which will return the secondPromise> promise. Then print the contents of the promise after it has been resolved by passing console.log to .then

```js
var secondPromise = new Promise((resolve, reject) => {
    resolve("Second!");
});
var firstPromise = new Promise((resolve, reject) => {
    resolve(secondPromise);
})

firstPromise.then(promise => promise)
    .then(value => console.log(value));
```

> CHALLENGE 7: We have a API that gets data from a database, it takes an index parameter and returns a promise Your challenge is to use Promise.all to make 3 API calls and return all the data when the calls are complete

```js
const fakePeople = [
    { name: 'Rudolph', hasPets: false, currentTemp: 98.6 },
    { name: 'Zebulon', hasPets: true, currentTemp: 22.6 },
    { name: 'Harold', hasPets: true, currentTemp: 98.3 },
]
const fakeAPICall = (i) => {
    const returnTime = Math.floor(Math.random() * 1000);
    return new Promise((resolve, reject) => {
        if (i >= 0 && i < fakePeople.length) {
            setTimeout(() => resolve(fakePeople[i]), returnTime);
        } else {
            reject({ message: "index out of range" });
        }
    });
};
function getAllData() {
    ar = [0, 1, 2];
    const items = ar.map(value => fakeAPICall(value));
    Promise.all(items).then((values) => {
        console.log(values);
    })
        .catch((data) => {
            console.log(data);
        });
}
getAllData();
```
### ITERATORS
  http://csbin.io/iterators

> CHALLENGE 1: Using setTimeout, print the string 'Hello!' after 1000ms.

```js
function sayHello() {
    setTimeout(() => {
        console.log("hello");
    }, 1000);
}

console.log("hi");
sayHello();
```

> CHALLENGE 2:Create a promise. Have it resolve with a value of 'Resolved!' in resolve after a delay of 1000ms, using setTimeout. Print the contents of the promise after it has been resolved by passing console.log to .then

```js
var promise = new Promise(function (resolve, reject) {
    setTimeout(resolve, 1000);
});

promise.then(() => {
    console.log("Resolved!");
})
```

> CHALLENGE 3: Create another promise. Now have it reject with a value of "Rejected!" without using setTimeout. Print the contents of the promise after it has been rejected by passing console.log to .catch

```js
var promise = new Promise(function (resolve, reject) {
    reject();
})
promise.catch(() => {
    console.log("Reject!");
})
```

> CHALLENGE 4: Promises are asynchronous and we're now going to prove that they indeed are! Create a promise and have it resolve with the value of "Promise has been resolved!" Then uncomment the code at bottom of Challenge 4. What order do we expect "Promise has been resolved!" and "I'm not the promise!" to print? Why?

```js
var promise = new Promise(function (resolve, reject) {
    resolve();
});

promise.then(() => console.log('Promise has been resolved!'));
console.log("I'm not the promise!");
```

> CHALLENGE 5: Write a function delay that returns a promise. And that promise should return a setTimeout that calls resolve after 1000ms

```js
function delay() {
    return new Promise(function (resolve, reject) {
        resolve();
    });
}
function sayHello() {
    setTimeout(() => {
        console.log("hello");
    }, 1000);
}
delay().then(sayHello);
```

> CHALLENGE 6: This challenge we'll chain promises together using ".then" Create two variables: firstPromise and secondPromise Set secondPromise to be a promise that resolves to "Second!" Set firstPromise to be a promise that resolves to secondPromise Call the firstPromise with a ".then", which will return the secondPromise> promise. Then print the contents of the promise after it has been resolved by passing console.log to .then

```js
var secondPromise = new Promise((resolve, reject) => {
    resolve("Second!");
});
var firstPromise = new Promise((resolve, reject) => {
    resolve(secondPromise);
})

firstPromise.then(promise => promise)
    .then(value => console.log(value));
```

> CHALLENGE 7: We have a API that gets data from a database, it takes an index parameter and returns a promise Your challenge is to use Promise.all to make 3 API calls and return all the data when the calls are complete

```js
const fakePeople = [
    { name: 'Rudolph', hasPets: false, currentTemp: 98.6 },
    { name: 'Zebulon', hasPets: true, currentTemp: 22.6 },
    { name: 'Harold', hasPets: true, currentTemp: 98.3 },
]
const fakeAPICall = (i) => {
    const returnTime = Math.floor(Math.random() * 1000);
    return new Promise((resolve, reject) => {
        if (i >= 0 && i < fakePeople.length) {
            setTimeout(() => resolve(fakePeople[i]), returnTime);
        } else {
            reject({ message: "index out of range" });
        }
    });
};
function getAllData() {
    ar = [0, 1, 2];
    const items = ar.map(value => fakeAPICall(value));
    Promise.all(items).then((values) => {
        console.log(values);
    })
        .catch((data) => {
            console.log(data);
        });
}
getAllData();
```
