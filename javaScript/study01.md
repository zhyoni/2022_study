#### ๐ญ ๊ณ ์ฐจํจ์ (high order function)
##### - ํจ์๊ฐ ํจ์๋ฅผ ๋ฆฌํดํ๋ ํจ์ (ํจ์์์ ํจ์๊ฐ ์๋ค. ํจ์๊ฐ ์ค๋ณต๋ ๋ ์ฌ์ฉ)

```javascript
const onClickOperator = (op) = {
  return () => {
    if(numOne){
      operator = op;
    }
  }
}

document.querySelector('#plus').addEventListener('click', onClickOperator('+'));

// ๊ณ ์ฐจํจ์ ์ฌ์ฉ
const onClickOperator = (op) = () => {
    if(numOne){
      operator = op;
    }
}
 // ()=>{ return ()=> {}} ์ด๊ฒฝ์ฐ ์ค๊ดํธ์ return์ด ๋ถ์ผ๋ฉด ์๋ต๊ฐ๋ฅํ๋ค. { return };์ ๊ฑฐ
```

<br>

#### ๐ญ if๋ฌธ ์ค์ฒฉ ์ค์ด๊ธฐ
##### 1. if๋ฌธ ๋ค์์ ๋์ค๋ ๊ณตํต๋ ์ ์ฐจ๋ฅผ ๊ฐ ๋ถ๊ธฐ์  ๋ด๋ถ์ ๋ฃ๋๋ค.
##### 2. ๋ถ๊ธฐ์ ์์ ์งง์ ์ ์ฐจ๋ถํฐ ์คํํ๊ฒ if๋ฌธ์ ์์ฑํ๋ค.
##### 3. ์งง์ ์ ์ฐจ๊ฐ ๋๋๋ฉด return(ํจ์ ๋ด๋ถ์ ๊ฒฝ์ฐ)์ด๋ break(for๋ฌธ ๋ด๋ถ์ ๊ฒฝ์ฐ)๋ก ์ค๋จํ๋ค.
##### 4. else๋ฅผ ์ ๊ฑฐํ๋ค(์ด๋ ์ค์ฒฉ ํ๋๊ฐ ์ ๊ฑฐ๋๋ค).
##### 5. ๋ค์ ์ค์ฒฉ๋ ๋ถ๊ธฐ์ ์ด ๋์ฌ ๋ 1~4์ ๊ณผ์ ์ ๋ฐ๋ณตํ๋ค.
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
// if๋ฌธ ๋ค์์ ๋์ค๋ ์ค๋ณต๋ ์ ์ฐจ ์ฐพ์์ ๊ฐ๊ฐ if๋ฌธ ์์ชฝ์ ๋ฃ์ด์ค๋ค.
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
// ๋ ์งง์ ๋จ๊ณ๋ฅผ ์๋ก ์ฌ๋ฆฐ๋ค.
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
// return๋ค์ else๊ฐ ํ์ ์์ผ๋ else๋ ์ง์์ค๋ค.
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
<!-- ๐๐๐๐๐๐๐๐๐๐๐๐๐ฃ๐ญ๐ฌ๐คก๐๐ถ๐ฅโญ๐โฆ๏ธ -->