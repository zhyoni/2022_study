#### 🍋 피셔-예이츠 셔플 알고리즘
#####  숫자를 무작위로 섞는 방법입니다. 먼저 무작위 인덱스를 하나 뽑은 후, 그에 해당되는 요소를 새로운 배열로 옮깁니다. 이를 반복하다 보면 새 배열에 무작위로 섞인 숫자들이 들어갑니다.

<br>

#### 🍋forEach()
##### forEach((element,index)=>{})
##### 배열의 있는 요소들을 forEach() 메서드로 순회합니다.
##### 인수로 함수를 받고, 배열의 요소 하나 하나에 인수로 받은 함수를 각각 적용한다. 이때 요소 순서대로 함수를 적용하므로 반복문의 역할을 하게 된다. 
<br>

```javascript
// for문사용
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
// forEach사용
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

#### 🍋 map()
##### map((element,index)=>{}) 
##### forEach역할도 하면서 return이 있어서 return에 적혀져있는데로 새로운 배열을 만든다. 이때 기존배열은 변경되지 않는다.
```javascript
// 각 배열에 2를 곱한값을 얻어오고 싶다면
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

#### 빈 배열 만들기
```javascript
// 원하는 배열의 길이 입력.어떤값으로 채울지 입력
Array(9)
// (9) [empty × 9]
Array(9).fill()
// (9) [undefined, undefined, undefined, undefined, undefined, undefined, undefined, undefined, undefined]
Array(9).fill(0)
// (9) [0, 0, 0, 0, 0, 0, 0, 0, 0]

Array(9).fill(0).map((el,idx)=>{
    return idx + 1;
})
// (9) [1, 2, 3, 4, 5, 6, 7, 8, 9]

```

