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

## day2

+ Date() : 날짜객체
+ getHours, getMinutes, getSeconds: 현재 시간, 초, 분
+ 시계를 만들기 위해 rotate 조정
+ setInterval(function,time) : time마다 function수행
+ transform-origin : 어디를 기준으로 애니메이션 수행할지 조절 (ex) 회전할때 어디를 축으로 회전할지


## day3

+ css 변수 : --를 앞에 붙이면 css변수로 사용할 수 있다 
```css
  :root{
      --base: #ffc600;
      --spacing: 10px;
      --blur: 10px;
    }
```
+ css 변수를 사용할때는 var()로 변수를 감싼다
```css
  img{
      padding: var(--spacing);
      background-color: var(--base);
      filter: blur(var(--blur));
    }
```
+ setProperty함수를 이용해 js에서 css속성을 변경할 수 있다
```javascript
  document.documentElement.style.setProperty(`--${this.name}`,this.value + suffix);
```
+ html태그안에 인라인 스타일을 이용해 css 변수를 설정하면 클로저이기 때문에 외부에서 변경 불가능한 css변수가 된다.
+ forEach함수를 이용해 이벤트를 설정할 수 있다.
```javascript
    inputs.forEach(input=>input.addEventListener('change',handleUpdate))
    inputs.forEach(input=>input.addEventListener('mousemove',handleUpdate))
```

## day4

### Array function
+ Array.prototype.filter() : 지정된 함수의 결과 값을 true로 만드는 원소들로만 구성된 별도의 배열을 반환
```javascript
      // 1500년대에 태어난 inventor의 배열
      const fifteen = inventors.filter(inventor=>inventor.year >= 1500 && inventor.year < 1600)
  ```
+ Array.prototype.sort() : 조건에 맞게 두 원소를 비교해 배열을 정렬한다.
```javascript
      // 나이순으로 inventor 정렬
      const oldest = inventors.sort((a,b)=>{
      const prevAge = a.passed-a.year;
      const nextAge = b.passed-b.year;
      return nextAge - prevAge;
    })
  ```
+ Array.prototype.map() : 배열을 이용해 조건에 맞는 새로운 배열을 반환
```javascript
      // inventor의 firstname과 lastname을 이용해 fullname 배열
      const fullName = inventors.map(inventor=> `${inventor.first} ${inventor.last}`)
  ```
+ Array.prototype.reduce() : 반복해서 배열의 값을 반환하는데 이것이 누적된다.
```javascript
    // inventor의 나이의 합
    const totalYear = inventors.reduce((total,inventor)=> total + (inventor.passed - inventor.year),0)
  ```
### ETC
+ console.table: console에 table형태로 출력해줌
+ 비구조화 할당
  ```javascript
      const [prevLast, prevFirst] = prev.split(', ')
      const [nextLast, nextFirst] = next.split(', ')
  ```
