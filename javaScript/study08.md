#### 💭 이차원 배열
##### 배열 안에 배열이 있을 때 이차원 배열이라고 한다. 
##### 배열이 몇 번 중첩됬느냐에 따라서 몇 차원 배열인지 정해진다. 표와 비슷한 모양이어서 실무에서 많이 사용한다.

```javascript
// 5(행)x4(열)의 이차원 배열을 만들고 배열의 요소는 모두 1로 만든다.
const array = [];
for (let i = 0; i < 5; i++) {
  const cell = [];
  for (let j = 0; j < 4; j++) {
    cell.push(1)
  }
  array.push(cell);
}
/*
    [1, 1, 1, 1]
    [1, 1, 1, 1]
    [1, 1, 1, 1]
    [1, 1, 1, 1]
    [1, 1, 1, 1]
*/
```
<br>

#### 💭 유사배열
##### 배열인척하지만 배열인척하는 객체이다
<br>

```javascript
  const array = [1, 2, 3]; // [1,2,3]
  const $div = document.querySelectorAll('div');
  const $ul = document.querySelector('ul');
  console.log($div) // NodeList(4) [div, div, div, div]
  console.log($ul.children) // HTMLCollection(5) [li, li, li, li, li]
```
<br>

##### 위 예제에서 모두 []로 감싸져 있지만 array만 배열이고, $div와 $ul은 유사배열이다.
##### Array.isArray 메서드(배열인지 판단해주는 메서드)를 사용해서 배열인지 확인할 수 있다.

<br>

```javascript
  Array.isArray(array) // false
  Array.isArray($div) // false
  Array.isArray($ul.children) // true
```
<br>

##### 배열과 유사배열을 구분해야 하는 이유는, 유사배열의 경우 배열의 메서드를 쓸 수 없기 때문이다.

<br>

```javascript
  array.forEach((el) => console.log(el)) //1, 2, 3
  $ul.forEach(function (el) { console.log(el) }) // Uncaught TypeError: $ul.forEach is not a function
  //forEach같은 배열 메서드를 사용하면 에러가 발생한다.

  $div.forEach(function (el) { console.log(el) }) // ( 프로토타입에 forEach가 있어서 된다.)
```
<br>

#### 💭 Array.from()
##### 유사 배열 객체는 Array.from() 메서드를 적용하면 배열이 되므로 indexOf 같은 배열의 메서드를 사용할 수 있다.
```javascript
  Array.from($ul.children).forEach((el, i) => {
    console.log($ul.children[i])
  })
```

<br>

#### 💭 배열.every(조건함수)
##### ♦️ every() 메서드는 반복문의 일종으로 요소를 순회하면서 조건 함수의 반환값이 모두 true면 every메서드도 true를 반환한다. 조건 함수의 반환값이 하나라도 false면 every 메서드의 반환값도 false가 된다.
##### ♦️ every 메서드는 일반 반복문 보다 더 효율적이다. 일반 반복문을 사용할 때는 직접 멈추지 않으면 끝까지 탐색하지만, every는 조건에 만족하지 않는 요소를 하나라도 찾으면 거기서 반복을 중단한다.
##### ♦️ <span style='background:yellowgreen'>모두 true여야 true 하나라도 false면 false</span>
##### ♦️ every()는 일차원 배열에서만 사용할 수 있다.

<br>

#### 💭 배열.some()
##### ♦️ <span style='background:yellowgreen'>하나라도 true여야 true 모두 false면 false</span>

##### ♦️ every와 some은 하나라도 예외가 있으면 함수를 바로 종료한다.

<br>

#### 💭 flat()
##### 배열의 차원을 한 단계 낮추는 메서드
##### 이차원 배열은 일차원 배열로 변경해주고, 삼차원 배열은 이차원 배열로 바꿔준다.
```javascript
// 이차원 배열 -> 일차원 배열
  const array = [[1,2,3], [4,5,6], [7,8,9]];
    // [1, 2, 3]
    // [4, 5, 6]
    // [7, 8, 9]
  array.flat(); // [1, 2, 3, 4, 5, 6, 7, 8, 9]
```
```javascript
// 삼차원 배열 -> 이차원 배열
  const array2 = [1, 2, 3, [[4, 5, 6], [7, 8, 9]]]; // [1, 2, 3, Array(2)]
  array2.flat(); // [1, 2, 3, Array(3), Array(3)]
```

<br>

#### 💭 filter()
##### 조건에 해당하는 요소를 걸러준다.
##### 일차원 배열에서만 사용가능.

<br>

#### 💭 rowIndex와 cellIndex
##### tr 태그는 몇 번째 줄인지 알려주는 rowIndex 라는 속성을 제공하고, tb 태그는 몇 번째 칸인지 알려주는 cellInex 라는 속성을 제공한다.

```javascript
const rowIndex = $tr.rowIndex;
const cellIndex = $td.cellIndex;
```