#### ๐ญ flag๋ณ์
##### let clickable = true; 
##### (true false) ์ฐธ ๊ฑฐ์ง์ผ๋ก ์คํํ๋์ง ํ์ง์๋์ง ๊ฒฐ์ ํด์ฃผ๋ ๋ณ์๋ฅผ ๋ณดํต flag๋ณ์๋ผ๊ณ  ํํํ๋ค.
###### * rap (๊ฐ์๋ฐ์๋ณด ๊ฒ์) [rsp.html](javaScript/5.๊ฐ์๋ฐ์๋ณด%20๊ฒ์/rsp.html) ์ฐธ๊ณ 
<br>

#### ๐ญ location.href ์ location.replace ์ฐจ์ด์ 
#### โฆ๏ธ location.href (์์ฑ)
##### ์๋ก์ด ํ์ด์ง๋ก ์ด๋๋๋ค.
##### ์ฃผ์ ํ์คํ ๋ฆฌ๊ฐ ๊ธฐ๋ก๋๋ค.
##### ์ฌ์ฉ ์) location.href='abc.php' 

<br>

#### โฆ๏ธ location.replace (๋ฉ์๋)
##### ๊ธฐ์กดํ์ด์ง๋ฅผ ์๋ก์ด ํ์ด์ง๋ก ๋ณ๊ฒฝ์ํจ๋ค.
##### ์ฃผ์ ํ์คํ ๋ฆฌ๊ฐ ๊ธฐ๋ก๋์ง ์๋๋ค.
##### ์ฌ์ฉ ์) location.replace('abc.php') 

<br>

#### ๐ญ location.reload() ๋ฉ์๋๋ ์๋ก ๊ณ ์นจ ๋ฒํผ๊ณผ ๊ฐ์ ํ์ฌ URL์ ๋ค์ ๋ก๋
```html
 <button type="button" onClick="reloadPage()">์๋ก๊ณ ์นจ</button>
```
```javascript
function reloadPage() {
  window.location.reload();
}
```