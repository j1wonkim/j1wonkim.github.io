---
title: "Promises and resolve()"
categories: ["Data Scientist Learning JS"]
date: 2026-08-11
permalink: /posts/2026/08/promises-and-resolve/
read_time: true
---

**Context:** I'm a data scientist/analyst (in Python and R) learning development from scratch. Inevitably, I am learning these through the lens of what I already know. If you have a similar background and are a beginner developer, I hope these analogies help! Any comments, especially if you spot any misunderstanding, are appreciated. Commenting is caring <3

## Motivation

I was building a mock data layer for a fitness social app — simulating what happens when users fetch new posts from a feed. The function needs to return mock posts after a delay, simulating a real network request.

## Working Code

```js
function fakeFetchPosts() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(posts);
    }, 2000);
  });
}

async function main() {
  console.log("Fetching...");
  const fetchedPosts = await fakeFetchPosts();
  console.log("Fetched posts:", fetchedPosts);
}

main();
console.log("Sync code ran");
```

**What do you expect to see as an output?**

I first confused the logic with blocking. For example, in web scraping, something like `time.sleep()` or Selenium's `WebDriverWait(driver, 10).until(EC.presence_of_element_located(...))`. In this case, I expected the output to be `Fetching...`, `Fetched posts: ...`, then `Sync code ran`.

However, the output gives `Fetching...`, `Sync code ran`, and then `Fetched posts: ...`.

In the former (blocking), the whole script (single thread) pauses and does nothing else until the wait ends or the condition is met. The latter is different in that the rest of your program keeps running during the wait, and thus `Sync code ran` gets printed before `fetchedPosts` resolves.

By the way, `posts` is an array:

```js
const posts = [
  {
    author: "j1wonkim",
    text: "Testing Physical",
    likes: 100,
  },
  {
    author: "onewc0218",
    text: "Love love",
    likes: 55,
  },
  {
    author: "gakbca",
    text: "You are good",
    likes: 10,
  },
];
```
