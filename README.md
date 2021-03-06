# memejs
Retrieve memes easily from reddit.
<p><a href="https://www.npmjs.com/package/memejs" rel="nofollow"><img src="https://badgen.net/npm/dt/memejs" alt="Downloads" /></a></p>

## Installation
```bash
npm install --save memejs
```

## Usage

`meme` can be called several ways:
- `meme()` which searches a random subreddit (from a list of allowable subreddits) and returns a promise
- `meme(subredit)` which searches the specified subreddit and returns a promise
- `meme(function(object, error))` which searches a random subreddit (from a list of allowable subreddits) and calls the callback function with the object on success, or with the error on failure
- `meme(subredit, function(object, error))` which searches the specified subreddit and calls the callback function with the object on success, or with the error on failure


To get the full JSON output:
```js
const { meme } = require('memejs');

meme(function(err, data) {
  if (err) return console.error(err);
  console.log(data);
});
```

To filter subreddits:
```js
const { meme } = require('memejs');

meme('crappydesign', function(err, data) {
  if (err) return console.error(err);
  console.log(data);
});
```

Async requests (DEPRECATED):
```js
const { memeAsync } = require('memejs');

memeAsync() // Use memeAsync('subredditname') to filter subreddits
.then(m => {
  // Do stuff with the JSON
  console.log(m);
})
.catch(e => {
  // Handle the error
  console.log(e);
})
```

Since promises can now be used automatically using the `meme` function that is the preferred method.
`memeAsync` will be removed in a future version.

TypeScript support:
```ts
import { memeAsync } from 'memejs';

memeAsync() // Use memeAsync('subredditname') to filter subreddits
.then(m => {  
  // Do stuff with the JSON
  console.log(m);
})
.catch(e => {
  // Handle the error
  console.log(e);
});
```

Example of JSON output:
```
{
  title: 'Me irl',
  url: 'https://i.redd.it/zdaqicupnzq41.jpg',
  author: 'godofeverythingelse',
  subreddit: 'me_irl',
  created: '2020-03-05 19:55:59.000',
  created_utc: '2020-03-05 11:55:59.000'
}
```

**Note:** You can now search for any subreddit.

Created by Kyle (Imposed#9787) and Nuno (nuno#4160). Refactor and tests created my [marshallasch](https://github.com/marshallAsch/).
