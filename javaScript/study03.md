#### ๐ญ forEach()
##### forEach((element,index)=>{})
##### ๋ฐฐ์ด์ ์๋ ์์๋ค์ forEach() ๋ฉ์๋๋ก ์ํํฉ๋๋ค.
##### ์ธ์๋ก ํจ์๋ฅผ ๋ฐ๊ณ , ๋ฐฐ์ด์ ์์ ํ๋ ํ๋์ ์ธ์๋ก ๋ฐ์ ํจ์๋ฅผ ๊ฐ๊ฐ ์ ์ฉํ๋ค. ์ด๋ ์์ ์์๋๋ก ํจ์๋ฅผ ์ ์ฉํ๋ฏ๋ก ๋ฐ๋ณต๋ฌธ์ ์ญํ ์ ํ๊ฒ ๋๋ค. 
<br>

```javascript
// for๋ฌธ์ฌ์ฉ
const answer = [3, 1, 4, 6];
const value = '3214';
let strike = 0;
let ball = 0;
for (let i = 0; i < answer.length; i++) {
  const index = value.indexOf(answer[i]);
  if (index > -1) {
    strike += 1;
  } else {
    ball += 1;
  }
}
```
```javascript
// forEach์ฌ์ฉ
answer.forEach((element, i) => {
  const index = value.indexOf(element);
  if (index > -1) {
    strike += 1;
  } else {
    ball += 1;
  }
})
```
<br>

#### ๐ญ map()
##### map((element,index)=>{}) 
##### forEach์ญํ ๋ ํ๋ฉด์ return์ด ์์ด์ return์ ์ ํ์ ธ์๋๋ฐ๋ก ์๋ก์ด ๋ฐฐ์ด์ ๋ง๋ ๋ค. ์ด๋ ๊ธฐ์กด๋ฐฐ์ด์ ๋ณ๊ฒฝ๋์ง ์๋๋ค.
```javascript
// ๊ฐ ๋ฐฐ์ด์ 2๋ฅผ ๊ณฑํ๊ฐ์ ์ป์ด์ค๊ณ  ์ถ๋ค๋ฉด
const array = [1, 2, 3, 4];
const result = [];
// for (let i = 0; i < 4; i++) {
//   result.push(array[i] * 2);
// }

array.map((element, index) => {
  return element * 2;
})
```
<br>

##### # ๋น ๋ฐฐ์ด ๋ง๋ค๊ธฐ
```javascript
// ์ํ๋ ๋ฐฐ์ด์ ๊ธธ์ด ์๋ ฅ.์ด๋ค๊ฐ์ผ๋ก ์ฑ์ธ์ง ์๋ ฅ
Array(9)
// (9)ย [empty ร 9]
Array(9).fill()
// (9)ย [undefined, undefined, undefined, undefined, undefined, undefined, undefined, undefined, undefined]
Array(9).fill(0)
// (9) [0, 0, 0, 0, 0, 0, 0, 0, 0]

Array(9).fill(0).map((el,idx)=>{
    return idx + 1;
})
// (9)ย [1, 2, 3, 4, 5, 6, 7, 8, 9]

```

