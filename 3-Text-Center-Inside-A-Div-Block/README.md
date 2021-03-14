# Div 블록 요소내 텍스트 정렬

## 알고 있는 것 & 새롭게 알게 된 것

- 흔히 알고 있는 중앙 정렬 방법
  ```css
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  ```

- 흔히 알고 있는 가로 중앙 정렬 방법
  ```css
  width: 400px;
  margin: 100px auto;
  ```

- 현재 예제에서는 내부 div가 가로 / 세로 중앙 정렬되어있다. 내부 div의 가로 중앙 정렬의 경우 `text-align`을 통해서 중앙 정렬 처리해주었다.

- `text-transform: uppercase;`를 통해서 소문자로 마크업된 문자열을 대문자로 보이도록 변경하였다.
