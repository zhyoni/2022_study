##### # 무작위 숫자를 뽑는 과정
##### Math.floor() 내림
##### Math.round() 반올림
##### Math.ceil() 올림

<br>

##### 💭 Math.random()은 암호학적으로 완전한 무작위다 아닙니다. 따라서 보안과 관련된 작업(예를 들어 비밀번호를 생성한다거나)을 할 때는 Math.random()으로 생성된 수를 사용하면 위험합니다. 이를 위한 window.crypto.getRandomValues() 함수가 따로 준비되어 있습니다.

```javascript
Math.random() // 0 <= x < 1
Math.random() * 9 // 0 <= x < 9
Math.random() * 9 + 1 // 1 <= x < 10
Math.floor(Math.random() * 9 + 1) 
// x = {1,2,3,4,5,6,7,8,9}
```

#### 💭 new Set() 
##### 중복을 허용하지 않는 특수한 배열. new는 예약어.
##### Set 내의 값은 유일해야 하기 때문에 값이 같은지 검사를 수행한다.
##### length가 아닌 size로 개수를 확인한다.

<br>

#### 💭 includes()
##### includes() 메서드는 인자로 전달된 값이 배열에 포함되어있으면 true를 반환하고 그렇지 않으면 false를 반환한다. (들어 있는지 없는지만 true or false로 알려줌)
```javascript
'2345'.includes(3) === true;
['2','3','4','5'].includes(5) === false;
```

<br>

#### indexOf()
##### 배열에서 지정된 요소를 찾을 수 있는 첫 번째 인덱스를 반환하고 존재하지 않으면 -1을 반환한다.
```javascript
'2345'.indexOf(3) === 1;
'2345'.indexOf(6) === -1;
['2','3','4','5'].indexOf('5') === 3;
['2','3','4','5'].indexOf(5) === -1; // 요소의 자료형까지 같아야 함

```
<br>

#### 💭 join() 
##### 배열의 모든 요소를 연결해 하나의 문자열로 만든다.
```javascript
const array = [1,2,3,4];
array.join() // 1,2,3,4
array.join('') // 1234
array.join('-') // 1-2-3-4
```
<br>

#### 💭 split()
##### string객체를 지정한 구분자를 이용하여 여러 개의 문자열로 나눈다.
```javascript
'3146'.split() // ['3146']
'3146'.split('') // ['3', '1', '4', '6']
'3146'.split(1) // ['3', '46'] 1을 기준으로 3과 46이 나뉜다.
```

<br>

#### splice()
##### 배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가하여 배열의 내용을 변경한다.
참고: https://hianna.tistory.com/396

