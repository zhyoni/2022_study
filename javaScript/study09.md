#### 💭 깊은 복사와 얕은 복사

```javascript
  const monsterList = [
      { name: '슬라임', hp: 25, att: 10, xp: 10 },
      { name: '스켈레톤', hp: 50, att: 15, xp: 20 },
      { name: '마왕', hp: 150, att: 35, xp: 35 },
    ];
```
##### JSON.parse(): JSON 문자열을 JavaScript 객체로 변환
##### JSON.stringify(): JavaScript 객체를 JSON 문자열로 변환

```javascript
// 간단한 객체는 JSON.parse(JSON.stringify(객체))를 사용해도 크게 문제는 없지만 성능도 느리고 함수나 Math, Date 같은 객체를 복사할 수 없다는 단점이 있다. 따라서 실무에서는 lodash 같은 라이브러리(다른 사람이 미리 만들어 둔 코드)를 사용하곤 한다.
  const monster1 = JSON.parse(JSON.stringify(monsterList[0]));
  const monster2 = monsterList[0];
  monster1.name = '새 몬스터';
  console.log(monsterList[0].name); // 슬라임
  monster2.name = '새 몬스터';
  console.log(monsterList[0].name); // 새 몬스터
  console.log(monsterList[0] === monster1); // false, 깊은 복사
  console.log(monsterList[0] === monster2); // true, 참조 관계

// 깊은 복사는 참조 관계가 전부 끊기고 전부 복사한다.
// 얕은 복사는 겉 껍데기만 복사하고 내부는 참조한다.
```

#### 얕은 복사(shallow copy)는 중첩된 객체가 있을 때 가장 바깥 객체만 복사되고 내부 객체는 참조 관계를 유지한다.
```javascript
  const array = [{ j: 'k' }, { l: 'm' }];
  const shallowCopy = [...array]; // 얕은 복사
  console.log(array === shallowCopy); // false
  console.log(array[0] === shallowCopy[0]); // true
```
##### 얕은 복사를 할 때는 ...연산자를 사용한다. 
##### ... 연산자를 spread 문법이라고 하는데, spread 문법은 기존 객체의 속성을 새 객체에 할당할 때 사용한다.
##### 배열이라면 [...배열]을 하면 되고, 객체라면 {...객체}를 하면 된다.
##### array와 shallowCopy 변수는 서로 다르지만, array[0]과 shallowCopy[0]은 같다.
##### 가장 바깥 객체는 복사되어 참조 관계가 끊어지므로 다른 값이 된다.

##### 얕은 복사할때에는 slice()를 사용해도 된다.

<br>

#### 깊은 복사
```javascript
const array = [{ j: 'k' }, { l: 'm' }];
const reference = array; // 참조
const deepCopy = JSON.parse(JSON.stringify(array)); // 깊은 복사
console.log(array === reference); // true

console.log(array[0] === reference[0]) // true
console.log(array === deepCopy) // false
console.log(array[0] === deepCopy[0]) // false



const a = 'b';
const c = ['d', true, 1];
const e = { g: 'h' };
const i = [{ j: 'k' }, { l: 'm' }];
const n = { o: { p: 'q' } };

const a1 = a;
const c1 = c.slice();//또는 [...c]
const e1 = { ...e };
const i1 = JSON.parse(JSON.stringify(i));
const n1 = JSON.parse(JSON.stringify(n));
```
