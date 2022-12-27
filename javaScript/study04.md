#### 💭 피셔-예이츠 셔플 알고리즘
#####  숫자를 무작위로 섞는 방법입니다. 먼저 무작위 인덱스를 하나 뽑은 후, 그에 해당되는 요소를 새로운 배열로 옮깁니다. 이를 반복하다 보면 새 배열에 무작위로 섞인 숫자들이 들어갑니다.

<br>

##### 💬 몇 번 반복해야할지 애매할때는 while 반복문을 쓰는게 좋다. 
##### 조건이 정확하거나 조건을 넣어야 할 때에는 for문을 사용하는게 좋다.

<br>

#### 💭 sort() 배열을 정렬하는 메서드
##### 배열의 요소를 적절한 위치에 정렬한 후 그 배열을 반환한다. 
###### sort(compareFunction(a,b)) a-b 오름차순 / b-a내림차순
```javascript
const array = ['6', '8', '3', '1', '9', '2'];
// 오름차순 정렬
const arr1 = array.sort((a, b) => a - b);
console.log(arr1);
// 내림차순 정렬
const arr2 = array.sort((a, b) => b - a);
console.log(arr2);

// 배열을 복사하지않고 sort()한 경우 기존 array배열도 바뀐다.
console.log(array) // ['9', '8', '6', '3', '2', '1']
```
```javascript
const arr1 = array.slice().sort((a, b) => a - b);
console.log(arr1);
// 내림차순 정렬
const arr2 = array.slice().sort((a, b) => b - a);
console.log(arr2);

// slice()를 사용하여 배열을 얕은 복사한 후 sort()한 경우 기존 array배열은 바뀌지 않는다.
console.log(array) // ['6', '8', '3', '1', '9', '2']
```
<br>

##### # 문자열을 정렬할 경우
```javascript
// 첫번째 글자의 코드넘버를 비교한다.
const arr = ['apple', 'orange', 'grape', 'banana', 'kiwi']

// 오름차순 정렬
const arr1 = arr.slice().sort((a, b) => a[0].charCodeAt() - b[0].charCodeAt());
console.log(arr1) // ['apple', 'banana', 'grape', 'kiwi', 'orange']

// 내림차순 정렬
const arr2 = arr.slice().sort((a, b) => b[0].charCodeAt() - a[0].charCodeAt());
console.log(arr2) // ['orange', 'kiwi', 'grape', 'banana', 'apple']

// 사전순으로 정렬
// 오름차순 정렬
const arr3 = arr.slice().sort((a, b) => a.localeCompare(b));
console.log(arr3) // ['apple', 'banana', 'grape', 'kiwi', 'orange']

// 내림차순 정렬
const arr4 = arr.slice().sort((a, b) => b.localeCompare(a));
console.log(arr4) // ['orange', 'kiwi', 'grape', 'banana', 'apple']

```

<br>

#### 💭 slice() 배열을 잘라내는 메서드
##### 어떤 배열의 begin 부터 end 까지(end 미포함)에 대한 얕은 복사본을 새로운 배열 객체로 반환한다.
##### 원본 배열은 바뀌지 않는다.
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

if / for / while / 함수 선언문의 중괄호 뒤에는 세미콜론이 붙지 않는다.