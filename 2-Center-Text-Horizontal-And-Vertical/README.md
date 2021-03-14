# 수평 / 수직 중앙 정렬

## 알고 있는 것 & 새롭게 알게 된 것

- 흔히 알고 있는 중앙 정렬 방법
  ```css
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  ```

  그나마 알고 있으면 좋은 것은 `position: absolute`는 가장 가까운 부모중에 `position: relative`를 찾아서 그것을 기준으로 정렬한다.