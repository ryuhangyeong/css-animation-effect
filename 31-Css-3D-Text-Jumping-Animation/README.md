# 3D 텍스트 점핑 애니메이션

## 영상을 보기에 앞서 생각해보기

- 사용 예상 속성들
  - `perspective`
  - `transformZ`
  - `box-shadow`
  - `@keyframes`
  - `animation-delay`

## 알고 있는 것 & 새롭게 알게 된 것

- 아래에 살짝 3D 효과(입체감)을 주는 부분을 `box-shadow`를 사용하였다. `box-shadow(x, y, blur, color)`이다.
- 예상과 다르게 구현된 부분이 많았다. `perspective, transformZ`를 사용하지 않았다. 내가 예상한 부분을 모두 `box-shadow`로 처리 했다.
- `@keyframes`를 이용해 각 애니메이션 단계마다 그림자를 중첩하여 효과를 주었다.
- 박스 안쪽 그림자 표현을 하려고 하는 경우 `inset` 사용! 이때 x, y축 기준이 달라진다. `inset`의 경우 (0, 0)이고 기본은 (0, y)라고 생각하면 될 듯하다.
