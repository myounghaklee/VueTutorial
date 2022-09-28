# VueTutorial

## Vue의 reactivity 사용 하는 방법
```javascript
    Object.defineProperty(대상 객체, 객체의 속성, {
        // 정의할 내용
     })
 ```


실제 예시 
```javascript
var viewModel= ();
(function() {
      function init() {
        Object.defineProperty(viewModel, 'str', {
          // 속성에 접근했을 때의 동작을 정의
          get: function() {
            console.log('접근');
          },
          // 속성에 값을 할당했을 때의 동작을 정의
          set: function(newValue) {
            console.log('할당', newValue);
            render(newValue);
          }
        });
      }

      function render(value) {
        div.innerHTML = value;
      }

```

- 즉시실행 함수 
```javascript
(function(){
    //code
})();
```
위처럼 코드를 작성하면 즉시실행되는 함수이다. 

## Vue instance
vue 인스턴스 객체의 값들은 `key : value` 형태로 들어오게 된다.

### 인스턴스에서 사용할 수 있는 속성, API 목록
- el : 인스턴스가 그려지ㅡㄴ 화면의 시작점( 특정 html 태그)
- template : 화면에 표시할 요서(html, css등) 
- data : 뷰의 reactivity가 반영된 데이터 속성
- method : 화면의 동작과 이벤트 로직을 제어하는 메서드 
- created : 뷰의 라이프 사이클과 관련된 속성 
- watch : data에서 정의한 속성이 변화했을때 추가 동갖을 수행할 수 있게 정의하는 속성

## Vue component
컴포넌트는 화면의 영역을 구분하여 개발할 수 잇는 뷰의 기능입니다. 컴포넌트 기반으로 화면을 개발하게 되면 코드의 재사용성이 올라가고 빠르게 화면을 제작할 수 있다.

