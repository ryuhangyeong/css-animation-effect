# 3D 카드 애니메이션

## 영상을 보기에 앞서 생각해보기

- `transform-origin`을 배웠기에 특정 축으로 회전하는 것은 알고 있음.
- 가장 큰 특징은 앞과 뒤의 표현을 어떻게 해줄까? 이다.

## 알고 있는 것 & 새롭게 알게 된 것

- `flex`를 사용하여 요소를 배치한다.
  기존 CSS 속성만으로 하기 힘든 배치를 손쉽게 할 수 있다.
- `perspective`를 이용하여 원근법 효과를 준다.
- `card` 부모를 기준으로 자식(`card-front`, `card-back`)을 배치하되 서로 겹치도록 한다. 부모에 `position`, 자식에 `absolute`를 사용
- `transform-style`
  기본 값은 `flat`로, 자식 요소는 2D의 2차원에서 부모 요소와 동일한 평면에 배치되지만, `transform-style: preserve-3d;`을 지정하여 3D 공간에 배치되도록 됩니다.

  `perspective`는 공간이 3D인거고 `transform-style: preserve-3d`는 요소가 3D

- `backface-visibility: hidden;` 요소의 뒷 부분을 보이지 않게 한다.

## 정리

> 굉장히 복합적인 테크니컬이 사용되어서 한번 정리해둘 필요가 있을 듯하다.

```html
<!-- wrap element - 원근법 표현 -->
<div class="cardBox">
  <div class="card facebook">
    <div class="card-front">Facebook</div>
    <div class="card-back">페이스북</div>
  </div>
</div>
```

- `cardBox`에 `hover` 하는 경우 `card`가 회전한다.
- `card`는 `front`와 `back`을 감싸는 wrap 요소
- 회전 후 뒷 부분을 보여주지 않기 위해 `backface-visibility: hidden` 사용
- `back`의 경우 `backface-visibility: hidden`를 설정하고 `rotate(180deg)`로 돌려놓으면 보여지지 않음.
- `back`을 보여주려면 `card`를 `rotate(180deg)`로 돌려주면 된다.
- 일부 속성의 작동 방법이 아직 모호하지만 앞으로 해야할 수많은 작업들을 하다보면 이해가 갈 듯하다.
