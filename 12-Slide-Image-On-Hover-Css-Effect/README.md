# 슬라이드 이미지 호버시 위로 끌어올려짐

## 영상을 보기에 앞서 생각해보기

- 부모 요소에 두개의 자식 요소가 있고 차례대로 쌓아올린 후 자식 요소를 감춘다. 감추기 위해 부모 요소에 `overflow: hidden`을 할 것
- 첫 번째 자식 요소를 호버하면서 `transform: translateY()`를 음수로 설정하면 아래 요소가 함께 올라올 것으로 예상

```css
/* 내가 작성해본 것 */
body {
  background-color: #1c363e;
  margin: 0;
  padding: 0;
}

.imageBox {
  width: 400px;
  height: 400px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #000;
  border-radius: 10px;
  box-shadow: 0 20px 25px rgba(0, 0, 0, 0.5);
  overflow: hidden;
}

.imageBox:hover img,
.imageBox:hover .textBox {
  transform: translateY(-100px);
}

.imageBox img {
  vertical-align: top;
  transition: all 0.2s;
}

.imageBox .textBox {
  background-color: red;
  transition: all 0.2s;
}

.imageBox .textBox p {
  width: 100%;
  margin: 0;
  padding: 0;
}
```

## 알고 있는 것 & 새롭게 알게 된 것

- ~~개인적으로 이번 강의에서 알려주신 방법은 좋지 않은 방법인 듯하다. 일단 마우스를 요소에 넣었다가 뺏다가를 반복하면 각 요소가 따로 따로 노는 듯한 느낌을 받는다. 이걸 의도하셨는진 모르겠지만 개인적으론 난 별로였다.(막상 깃헙 페이지에서 확인해보니 이 현상이 일어나지 않는다. 뭐지? 분명히 로컬에서 할 때는 막 흔들렸는데..)~~

- 자식 요소가 부모 요소를 채우는 경우

```css
top: 0;
right: 0;
bottom: 0;
left: 0;
```

을 주로 사용하였는데. `top: 0; width: 100%; height: 100%`를 사용하면 쉽게 할 수 있다는 것을 알게 되었고 자식요소에서 `top: 100%`를 하면 부모 요소 높이만큼 포지셔닝이 먹는다는 것을 알게 되었다. 예제에서는 `bottom`으로 했지만 `top`과 동일하다.

- `textBox`의 경우 `bottom`을 `-100% -> -65%`로 주어서 아래 숨겨져있던 텍스트 박스를 위로 끌어올려준다. 그 다음 이미지도 끌어올려야하는데 이미지는 `100 - 65`인 `-35%`만큼만 올려준다. 쉽게 말하면 텍스트 박스가 `-100%`에서 `-65%` 보여진다는 것은 실질적으로 `35%`를 보여준다는 것을 의미한다. 그리고 텍스트가 `35%`만큼 보여진 만큼 반대로 이미지는 `35%`만큼 위로 올려서 숨겨줘야한다.

- 간단한 내용이지만 이거가지고 이런 저런 생각을 해보면서 공부를 해보아서 도움이 되었다.
