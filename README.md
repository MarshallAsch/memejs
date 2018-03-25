# memejs
Get the best memes with ease!

## Installation
```bash
npm install memejs
```

## Usage
To get the full JSON output:
```js
var meme = require('memejs');

meme(function(data, err) {
  if (err) return console.error(err);
  console.log(data);
});
```
To get the meme title:
```js
var meme = require('memejs');

meme(function(data, err) {
  if (err) return console.error(err);
  console.log(data.title[0]);
});
```
To get the meme url:
```js
var meme = require('memejs');

meme(function(data, err) {
  if (err) return console.error(err);
  console.log(data.url[0]);
});
```
To get the author:
```js
var meme = require('memejs');

meme(function(data, err) {
  if (err) return console.error(err);
  console.log(data.author[0]);
});
```
To get the time the meme was created:
```js
var meme = require('memejs');

meme(function(data, err) {
  if (err) return console.error(err);
  console.log(data.created[0]);
});
```
To get the UTC time the meme was created:
```js
var meme = require('memejs');

meme(function(data, err) {
  if (err) return console.error(err);
  console.log(data.created_utc[0]);
});
```
