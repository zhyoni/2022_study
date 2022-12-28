#### 💭 flag변수
##### let clickable = true; 
##### (true false) 참 거짓으로 실행하는지 하지않는지 결정해주는 변수를 보통 flag변수라고 표현한다.
###### * rap (가위바위보 게임) [rsp.html](javaScript/5.가위바위보%20게임/rsp.html) 참고
<br>

#### 💭 location.href 와 location.replace 차이점
#### ♦️ location.href (속성)
##### 새로운 페이지로 이동된다.
##### 주소 히스토리가 기록된다.
##### 사용 예) location.href='abc.php' 

<br>

#### ♦️ location.replace (메서드)
##### 기존페이지를 새로운 페이지로 변경시킨다.
##### 주소 히스토리가 기록되지 않는다.
##### 사용 예) location.replace('abc.php') 

<br>

#### 💭 location.reload() 메서드는 새로 고침 버튼과 같은 현재 URL을 다시 로드
```html
 <button type="button" onClick="reloadPage()">새로고침</button>
```
```javascript
function reloadPage() {
  window.location.reload();
}
```