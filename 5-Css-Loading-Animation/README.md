# CSS 로딩 애니메이션

## 알고 있는 것 & 새롭게 알게 된 것

- 나는 `transform: translateX`를 사용할 때 1차원적으로 X축으로 이동하는 것이라 생각했다. 근데 이번 예제를 실행하면서 알게된 것은 X축으로 이동하되 3차원적인 요소를 가지고 이동된다는 것을 알게 되었다. 쉽게 설명하자면 X축으로 이동하되 붕 떠있는 상태로 이동하는 것이다. 붕 떠있다는 것은 뭘 의미할까? 그림자를 표현할 수 있다는거다!
`transform: translateY(0); -> transform: translateY(-15px);`가 된다면 -15px 만큼 Y축으로 붕뜬다고 생각하면 된다. 그리고 그 사이에 그림자를 표현한다면 떠올랐다가 내려가는 효과를 더 극적으로 보여줄 수 있다.
여기에 `margin-left: 10px;`를 각 요소마다 주면 사이 간격이 넓어지면서 커지는 듯한 효과를 준다.
다음에는 각 요소마다 `animation-delay` 값을 다르게 준다. 
- `text-shadow`
```css
/* offset-x | offset-y | blur-radius | color */
text-shadow: 1px 1px 2px black;
```