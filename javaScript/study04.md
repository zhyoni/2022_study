#### ๐ญ ํผ์-์์ด์ธ  ์ํ ์๊ณ ๋ฆฌ์ฆ
#####  ์ซ์๋ฅผ ๋ฌด์์๋ก ์๋ ๋ฐฉ๋ฒ์๋๋ค. ๋จผ์  ๋ฌด์์ ์ธ๋ฑ์ค๋ฅผ ํ๋ ๋ฝ์ ํ, ๊ทธ์ ํด๋น๋๋ ์์๋ฅผ ์๋ก์ด ๋ฐฐ์ด๋ก ์ฎ๊น๋๋ค. ์ด๋ฅผ ๋ฐ๋ณตํ๋ค ๋ณด๋ฉด ์ ๋ฐฐ์ด์ ๋ฌด์์๋ก ์์ธ ์ซ์๋ค์ด ๋ค์ด๊ฐ๋๋ค.

<br>

##### ๐ฌ ๋ช ๋ฒ ๋ฐ๋ณตํด์ผํ ์ง ์ ๋งคํ ๋๋ while ๋ฐ๋ณต๋ฌธ์ ์ฐ๋๊ฒ ์ข๋ค. 
##### ์กฐ๊ฑด์ด ์ ํํ๊ฑฐ๋ ์กฐ๊ฑด์ ๋ฃ์ด์ผ ํ  ๋์๋ for๋ฌธ์ ์ฌ์ฉํ๋๊ฒ ์ข๋ค.

<br>

#### ๐ญ sort() ๋ฐฐ์ด์ ์ ๋ ฌํ๋ ๋ฉ์๋
##### ๋ฐฐ์ด์ ์์๋ฅผ ์ ์ ํ ์์น์ ์ ๋ ฌํ ํ ๊ทธ ๋ฐฐ์ด์ ๋ฐํํ๋ค. 
###### sort(compareFunction(a,b)) a-b ์ค๋ฆ์ฐจ์ / b-a๋ด๋ฆผ์ฐจ์
```javascript
const array = ['6', '8', '3', '1', '9', '2'];
// ์ค๋ฆ์ฐจ์ ์ ๋ ฌ
const arr1 = array.sort((a, b) => a - b);
console.log(arr1);
// ๋ด๋ฆผ์ฐจ์ ์ ๋ ฌ
const arr2 = array.sort((a, b) => b - a);
console.log(arr2);

// ๋ฐฐ์ด์ ๋ณต์ฌํ์ง์๊ณ  sort()ํ ๊ฒฝ์ฐ ๊ธฐ์กด array๋ฐฐ์ด๋ ๋ฐ๋๋ค.
console.log(array) // ['9', '8', '6', '3', '2', '1']
```
```javascript
const arr1 = array.slice().sort((a, b) => a - b);
console.log(arr1);
// ๋ด๋ฆผ์ฐจ์ ์ ๋ ฌ
const arr2 = array.slice().sort((a, b) => b - a);
console.log(arr2);

// slice()๋ฅผ ์ฌ์ฉํ์ฌ ๋ฐฐ์ด์ ์์ ๋ณต์ฌํ ํ sort()ํ ๊ฒฝ์ฐ ๊ธฐ์กด array๋ฐฐ์ด์ ๋ฐ๋์ง ์๋๋ค.
console.log(array) // ['6', '8', '3', '1', '9', '2']
```
<br>

##### # ๋ฌธ์์ด์ ์ ๋ ฌํ  ๊ฒฝ์ฐ
```javascript
// ์ฒซ๋ฒ์งธ ๊ธ์์ ์ฝ๋๋๋ฒ๋ฅผ ๋น๊ตํ๋ค.
const arr = ['apple', 'orange', 'grape', 'banana', 'kiwi']

// ์ค๋ฆ์ฐจ์ ์ ๋ ฌ
const arr1 = arr.slice().sort((a, b) => a[0].charCodeAt() - b[0].charCodeAt());
console.log(arr1) // ['apple', 'banana', 'grape', 'kiwi', 'orange']

// ๋ด๋ฆผ์ฐจ์ ์ ๋ ฌ
const arr2 = arr.slice().sort((a, b) => b[0].charCodeAt() - a[0].charCodeAt());
console.log(arr2) // ['orange', 'kiwi', 'grape', 'banana', 'apple']

// ์ฌ์ ์์ผ๋ก ์ ๋ ฌ
// ์ค๋ฆ์ฐจ์ ์ ๋ ฌ
const arr3 = arr.slice().sort((a, b) => a.localeCompare(b));
console.log(arr3) // ['apple', 'banana', 'grape', 'kiwi', 'orange']

// ๋ด๋ฆผ์ฐจ์ ์ ๋ ฌ
const arr4 = arr.slice().sort((a, b) => b.localeCompare(a));
console.log(arr4) // ['orange', 'kiwi', 'grape', 'banana', 'apple']

```

<br>

#### ๐ญ slice() ๋ฐฐ์ด์ ์๋ผ๋ด๋ ๋ฉ์๋
##### ์ด๋ค ๋ฐฐ์ด์ begin ๋ถํฐ end ๊น์ง(end ๋ฏธํฌํจ)์ ๋ํ ์์ ๋ณต์ฌ๋ณธ์ ์๋ก์ด ๋ฐฐ์ด ๊ฐ์ฒด๋ก ๋ฐํํ๋ค.
##### ์๋ณธ ๋ฐฐ์ด์ ๋ฐ๋์ง ์๋๋ค.
```javascript
const array = ['a', 'b', 'c', 'd', 'e', 'f'];
// array index 0,1,2,3,4,5

const arr1 = array.slice(0, 2)
console.log(arr1) // ['a', 'b']

const arr2 = array.slice(0, 5);
console.log(arr2) // ['a', 'b', 'c', 'd', 'e']

const arr3 = array.slice(2, -1);
console.log(arr3) // ['c', 'd', 'e']
```

if / for / while / ํจ์ ์ ์ธ๋ฌธ์ ์ค๊ดํธ ๋ค์๋ ์ธ๋ฏธ์ฝ๋ก ์ด ๋ถ์ง ์๋๋ค.