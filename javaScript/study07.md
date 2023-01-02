#### 💭 구조분해 할당
##### 배열이나 객체의 속성을 해체하여 그 값을 개별 변수에 담을 수 있게 하는 JavaScript 표현식

<br>

```javascript
// 객체에 대한 구조분해 할당
// 객체 내부의 속성과 할당하는 변수명이 같아야 한다.
// 여러 개의 속성을 동시에 변수에 할당할 수도 있다.
  const { body } = document; // === const body = document.body; 

/*---------------------------------------------------------------*/

  const arr = [1,2,3,4,5];

  const one = arr[0]; 
  const two = arr[1];
  const three = arr[2];
  const four = arr[3];
  const five = arr[4]; 

           ⇩ //(이렇게 쓸 수 있다.)
         
// 배열에 대한 구조분해 할당
// 자릿수가 동일해야 한다.
  const [one,two,three,four,five] = arr;

// 만약 1,3,5만 사용하고 2,4는 사용하지 않는다면
  const [one,,three,,five] = arr; // two와 four 자리를 지운뒤 콤마는 그대로 둔다. 

/*---------------------------------------------------------------*/

// # 여러 개의 속성을 변수에 넣는 경우
  const obj = { a: 1, b: 2 };
  const a = obj.a; // 1
  const b = obj.b; // 2

            ⇩

  const { a, b } = obj;
  console.log(obj, a, b) // {a: 1, b: 2} 1 2

// obj에 c를 추가하고 싶다면
  obj.c = 3;
  const { a, b, c } = obj; // c를 추가해주면 된다.
  console.log(obj, a, b, c) //{a: 1, b: 2, c: 3} 1 2 3

/*---------------------------------------------------------------*/

// a,c,e 속성을 구조분해 할당 문법으로 변수에 할당해보자.
  const obj = {
    a: 'hello',
    b: {
      c: 'hi',
      d: { e: 'wow' }
    }
  };
  const { a, b: { c, d: { e } } } = obj;

// 만약 b를 구조분해 할당하고 싶다면
  const { a, b } = obj;
  const { d: { e } } = b;
```

<br>

#### 💭 이벤트 버블링(bubbling)
##### 한 요소에 이벤트가 발생하면, 이 요소에 할당된 핸들러가 동작하고, 이어서 부모 요소의 핸들러가 동작합니다. 가장 최상단의 조상 요소를 만날 때까지 이 과정이 반복되면서 요소 각각에 할당된 핸들러가 동작합니다.
<br>

```javascript
// FORM > DIV > P 형태로 중첩된 구조 살펴보기.
<form onclick="alert('form')">FORM
  <div onclick="alert('div')">DIV
    <p onclick="alert('p')">P</p>
  </div>
</form>
```
```text
가장 안쪽의 <p>를 클릭하면 다음과 같이 실행된다.
1. <p>에 할당된 onclick 핸들러가 동작한다.
2. 바깥의 <div>에 할당된 핸들러가 동작한다.
3. 그 바깥의 <form>에 할당된 핸들러가 동작한다.
4. document 객체를 만날 때까지, 각 요소에 할당된 onclick 핸들러가 동작한다.

p → div → form 순서로 3개의 얼럿 창 실행됨.

거의 모든 이벤트는 버블링이 되지만, focus이벤트 같이 버블링 되지 않는 이벤트도 있다.
```

<br>

#### 💭 event.target
##### 이벤트가 발생한 가장 안쪽의 요소는 타깃(target) 요소라고 불리고, event.target을 사용해 접근할 수 있다.

#### 💭 event.target과 this(=event.currentTarget)의 차이점
##### event.target은 <span style='text-decoration: underline'>실제 이벤트가 시작된 ‘타깃’ 요소</span>입니다. 버블링이 진행되어도 변하지 않습니다.
##### this는 ‘현재’ 요소로, 현재 실행 중인 이벤트 핸들러가 할당된 요소를 참조합니다. <span style='text-decoration: underline'>(내가 이벤트를 붙인 '타깃' 요소)</span>

```html
 <form id="form">FORM
    <div>DIV
      <p>P</p>
    </div>
  </form>
```
```javascript
form.onclick = function (event) {
  console.log(event.target);
  // form click -> event.target === form
  // div click -> event.target === div
  // p click -> event.target === p
  console.log(this); // form
  console.log(event.currentTarget); // form
  this === event.currentTarget ? console.log(true):console.log(false) // true
 };
```
<br>

#### 💭 버블링 중단하기
##### 이벤트 객체의 메서드인 <span style='text-decoration: underline'> event.stopPropagation()</span>를 사용하면 핸들러에게 이벤트를 완전히 처리하고 난 후 버블링을 중단하도록 명령할 수 있다.
##### event.stopPropagation()은 위쪽으로 일어나는 버블링은 막아주지만, 다른 핸들러들이 동작하는 건 막지 못한다.

<br>

##### 버블링을 멈추고, 요소에 할당된 다른 핸들러의 동작도 막으려면
##### event.stopImmediatePropagation()을 사용해야 한다. 이 메서드를 사용하면 요소에 할당된 특정 이벤트를 처리하는 핸들러 모두가 동작않는다.

<br>

#### 이벤트 캡처링 
##### 부모에서 발생한 이벤트가 자식한테 발생하는 것
##### ex.) 이벤트 캡처링을 사용하는 경우는 보통 팝업을 닫을때 팝업 바깥쪽을 클릭하면 팝업이 닫히게 되는 경우 사용을 많이 한다.
참고: [https://ko.javascript.info/bubbling-and-capturing#ref-528]
```javascript
 // 태그.addEventListener('click',()=>{}, true);기본값 false true를 명시해주면 이벤트캡처링이 된다.
```