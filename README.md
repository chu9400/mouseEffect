## mouseEffect 학습 저장소

### 01. jQuery hover 문법

- 문법
```javascript
$(".select").hover(
    function() {}, // mousehover 했을 때
    function() {}, // mouseout 되었을 때
)
```

- 예시
```javascript
$(".mouseCont span").hover(
    function() { 
        $(".cursor").addClass($(this).attr("class")); 
    }, 
    function() { 
        $(".cursor").removeClass($(this).attr("class"));
    }
);

```        


### 02. gsap 문법
- duration 효과
    duration의 값을 각각 다르게하여 챕터2의 따라다니기 기능 구현 가능
```javascript
    gsap.to(cursor, {
        duration:0.3, 
        left: e.pageX -5, 
        top: e.pageY - 5,
    });

    gsap.to(follower, {
        duration:0.8, 
        left: e.pageX - 15, 
        top: e.pageY - 15,
    });
```

### 03. 마우스 커서 브랜딩 효과
```css
    .cursor {
        position: absolute;
        left: 0; top: 0;
        width: 10px;
        height: 10px;
        border-radius: 50%;
        z-index: 9999;
        background-color: #fff;
        user-select: none;
        pointer-events: none;
        transition: transform 0.3s;
        mix-blend-mode: difference;
    }
```

- 주목해야할 코드
    mix-blend-mode: difference;
    이 코드는 자신의 배경과 그 위의 요소의 배경을 혼합하는 디자인 효과를 줄 수 있음.
    