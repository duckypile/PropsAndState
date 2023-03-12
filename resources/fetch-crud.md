# Reference for `fetch` API, using CRUD verbs

Note: [Official Docs Here](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch#Supplying_request_options)

CRUD:
|Letter |Stands For |Verb |Use Case |
|--- |--- |--- |--- |
|C |Create |POST |Making new data |
|R |Read |GET |Fetching pre-existing data|
|U |Update |PATCH |Editing Data|
|D |Destroy |DELETE |Removing Data |

## POST

Example use cases: login/register, creating new data in DB

```js
const response = await fetch('https://url.com/', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    Authorization: `Bearer ${token}`,
  },
  body: JSON.stringify({
    // our data TO CREATE here
  }),
});
const data = await response.json();
```

## GET

Example use cases: Fetching news posts, getting account data.

### Simple unauthenticated fetch

```js
const response = await fetch('https://url.com/');
const data = await response.json();
```

### With Authorization token (i.e. for getting my user data)

```js
const response = await fetch(`https://url.com/me`, {
  headers: {
    'Content-Type': 'application/json',
    Authorization: `Bearer ${token}`,
  },
});
const data = await response.json();
```

## PATCH

Example use cases: Editing something in a Database, making changes to any data.

```js
const response = await fetch(`https://url.com/${id}`, {
  method: 'PATCH',
  headers: {
    'Content-Type': 'application/json',
    Authorization: `Bearer ${token}`,
  },
  body: JSON.stringify({
    // our NEW/UPDATED data here
  }),
});
const data = await response.json();
```

## DELETE

Example use cases: Removing a post, deleting a profile picture, deleting a message.

```js
const response = await fetch(`https://url.com/${id}`, {
  method: 'DELETE',
  headers: {
    'Content-Type': 'application/json',
    Authorization: `Bearer ${token}`,
  },
});
const data = await response.json();
```
