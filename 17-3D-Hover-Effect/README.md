# 3D 위 아래 슬라이드 배너 효과

## 영상을 보기에 앞서 생각해보기

- `rotateX`로 아래로 회전하는 것으로 예상된다.
- 요소가 위 아래로 쌓여있기 때문에 두 요소 모두에게 효과를 주어야 할듯.

## 알고 있는 것 & 새롭게 알게 된 것

- `transform-style: preserve-3d`
  자식 요소를 3D 공간에 배치하거나 2D 평면에 평평하게 배치 할지를 지정하기

- `backface-visibility: hidden;`
  요소의 뒷쪽에서 앞면이 보이게 할지 정하는 속성, 기본적으로 `180deg` 회전하면 앞 모습이 반전된 상태로 보이는데 이것을 숨기고 싶은 경우 사용한다.

- `perspective`
  원근법, 숫자가 커질수록 멀리서 보는 느낌이 난다.

- `transform-origin`
  회전 기준

- `transform: translateY(50%)`
  현재 요소의 높이 혹은 크기의 절반만큼 이동

  ![translateY](https://user-images.githubusercontent.com/27342882/112237455-0d34c300-8c86-11eb-8f1c-3ef9689f1bfc.PNG)

- 분석

  ```css
  .main .top {
    background-color: #e22927;
    color: #fff;
    /*
      자신의 위치에서 자신의 크기 혹은 높이 절반만큼 위로 올라간
      상태에서 회전
     */
    transform: rotateX(90deg) translateY(-50%);
    transform-origin: top center;
  }

  .main:hover .top {
    /* 원상 복구 */
    transform: rotateX(0deg) translateY(0%);
  }
  ```

  이건 추측이지만 원근법(`perspective`)을 주기 위해서 `translateY`가 필요한 것 같다.
