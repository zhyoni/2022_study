##### 🍋 고차함수 (high order function)
##### - 함수가 함수를 리턴하는 함수 (함수안에 함수가 있다. 함수가 중복될때 사용)

```javascript
const onClickOperator = (op) = {
  return () => {
    if(numOne){
      operator = op;
    }
  }
}

document.querySelector('#plus').addEventListener('click', onClickOperator('+'));

// 고차함수 사용
const onClickOperator = (op) = () => {
    if(numOne){
      operator = op;
    }
}
 // ()=>{ return ()=> {}} 이경우 중괄호와 return이 붙으면 생략가능하다. { return };제거
```

<br>

##### 🍋 if문 중첩 줄이기
##### 1. if문 다음에 나오는 공통된 절차를 각 분기점 내부에 넣는다.
##### 2. 분기점에서 짧은 절차부터 실행하게 if문을 작성한다.
##### 3. 짧은 절차가 끝나면 return(함수 내부의 경우)이나 break(for문 내부의 경우)로 중단한다.
##### 4. else를 제거한다(이때 중첩 하나가 제거된다).
##### 5. 다음 중첩된 분기점이 나올 때 1~4의 과정을 반복한다.
<br>

```javascript
ex)
function test() {
  let result = '';
  if (a) {
    if (!b) {
      result = 'c';
    }
  } else {
    result = 'a';
  }
  result += 'b';
  return result;
}
```
```javascript
// if문 다음에 나오는 중복된 절차 찾아서 각각 if문 안쪽에 넣어준다.
function test() {
  let result = '';
  if (a) {
    if (!b) {
      result = 'c';
    }
    result += 'b';
    return result;
  } else {
    result = 'a';
    result += 'b';
    return result;
  }
}
``` 
```javascript
// 더 짧은 단계를 위로 올린다.
function test() {
  let result = '';
  if (!a) {
     result = 'a';
    result += 'b';
    return result; 
  } else {
    if (!b) {
      result = 'c';
    }
    result += 'b';
    return result;
  }
}
```
```javascript
// return뒤에 else가 필요 없으니 else는 지워준다.
function test() {
  let result = '';
  if (!a) {
     result = 'a';
    result += 'b';
    return result; 
  } 
  if (!b) {
    result = 'c';
  }
  result += 'b';
  return result;
}
```
<!-- 🍓🍑🍊🍋🍏🍎🍒🍇🍈🍍🍌💛💣💭💬🤡🙀🐶🔥⭐🌎♦️ -->