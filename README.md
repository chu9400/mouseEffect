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
---

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

---

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

- 주목 코드 : mix-blend-mode: difference;
- 이 코드는 자신의 배경과 그 위의 요소의 배경을 혼합하는 디자인 효과를 줄 수 있음.
    
---

### 04-01. 조명 효과

```css
    .cursor{
        position: absolute;
        width: 200px;
        height: 200px;
        border-radius: 50%;
        border: 5px solid #fff;
        background-image: url(./img/bg6.jpg);
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        background-attachment: fixed;
        z-index: -1;
    }
```

- 주목 코드 : background-attachment: fixed;
- 배경 이미지가 움직이지 않고 고정되게 하는 코드이다. 사용자가 페이지를 스크롤해도 배경 이미지는 움직이지 않고 화면에 고정된다.

- 배경이미지가 뒤에 있는 디자인 효과를 줄 수 있다.

---

### 04-02 요소의 가로 세로값 구하는 법 javascript 고급편
```javascript
    const circle = cursor.getBoundingClientRect();
    
    gsap.to(cursor, {
        duration:0.3,
        left:e.pageX - circle.width/2,
        top:e.pageY - circle.height/2,
    });
```
getBoundingClientRect함수를 사용하여 출력해보면
![Alt text](image.png)
이런 값이 나온다.