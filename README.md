# Text Editor

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[checkout the site!](https://infinite-tor-98163.herokuapp.com/)

![ScreenShot](./assets/images/chrome_fGvCJycRmC.png)

## Description
This application is a Text Editor that runs in the browser which uses the IndexedDB API. I built this application to learn to build progressive web applications.

## Technology Used
* IndexedDB
* express
* if-env
* PWA
* Node.js
* Webpack

## Code Snippet
Here I have logic that provides a way to accept content and add it to the database

```JavaScript
export const putDb = async (content) => {
  try {
    const jateDb = await openDB("jate", 1);
    const tx = jateDb.transaction("jate", "readwrite");
    const store = tx.objectStore("jate");
    const request = store.add({ id: 1, value: content });
    const result = await request;
  } catch (err) {
    console.log(err);
  }
};
```
Similiarly here I wrote logic to get all the content from the database
```JavaScript
export const getDb = async () => {
  try {
    const jateDb = await ("jate", 1);
    const tx = jateDb.transaction("jate", "readonly");
    const store = tx.objectStore("jate");
    const request = store.get(1);
    const result = await request;
    return result.value;
  } catch (error) {
    console.log(error);
  }
};
```

## Author links
* [GitHub](https://github.com/mattjgatsby)
* [LinkedIn](https://www.linkedin.com/in/matthew-gatsby-1a1521250/)