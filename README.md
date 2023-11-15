## mouseEffect 학습 저장소

### 01. jQuery hover 문법

- 문법
```
$(".select").hover(
    function() {}, // mousehover 했을 때
    function() {}, // mouseout 되었을 때
)
```

- 예시
```
$(".mouseCont span").hover(
    function() { 
        $(".cursor").addClass($(this).attr("class")); 
    }, 
    function() { 
        $(".cursor").removeClass($(this).attr("class"));
    }
);

```        
