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

