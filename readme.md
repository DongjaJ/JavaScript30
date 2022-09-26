![](https://javascript30.com/images/JS3-social-share.png)

# JavaScript30 challenge

## day 1

+ attribute selecor: queryselector로 태그, 클래스, id뿐만 아니라 속성으로도 접근 가능
+ 태그
  + audio 태그 : 소리를 출력하는 태그
    + play: 출력 , currentTime: 소리 출력할때마다 리셋
  + kbd 태그 : 키보드 모양 태그
+ 클래스 추가, 삭제
```javascript
  const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);
  key.classList.add('playing');
  key.classList.remove('playing');
```
+ 이벤트
  + keydown : 키가 눌렸을 때 이벤트
  + transitioned : transition 애니메이션 끝났을 때 이벤트
  + e.propertyName: 이벤트 애니메이션과 관련된 속성, 원하는 이벤트만 걸러낼수 있다  ex) transform

