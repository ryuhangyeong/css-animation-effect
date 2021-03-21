# 확대 / 축소 효과가있는 멋진 상자

## 영상을 보기에 앞서 생각해보기

- 상자안의 동그란 A가 확정되면서 밑으로 내려왔다가 다시 올라간 후 텍스트 영역이 보임

- 테두리(?) 비슷한게 사라졌다 생김. 근데 4방향 모두 생긴다. 정확히는 `border`가 아닌거 같은데 도대체 뭘로 이걸 만든걸까? 이건 잘 모르겠다.

## 알고 있는 것 & 새롭게 알게 된 것

- 근데 왜 생각해보니 테두리 부분은 왜 안하신거지..? 흐음..
- 이번 영상의 코드는 라인별로 하나씩 분석해가며 왜 이렇게 해야하는지 추론해보자. (사실 몇몇 부분은 왜 이렇게 해야하는지 잘 모르겠다.)

```css
.container .icon {
  height: 50px;
  line-height: 50px;
  width: 50px;
  background-color: #262626;
  border-radius: 50%;
  color: #fff;
  transition: all 0.5s ease;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}
```

코드를 보고 들었던 의문은 왜 가로 중앙 정렬을 할 때 `position`을 쓸까? 였다. 단순히 블록 요소이므로 `text-align`을 쓰면 되는거 아니야?라는 생각이 들었는데. 실제로 `text-align`을 사용하고 테스트해보았더니 왜 `position`을 썻는지 이해할 수 있었다.

```css
.container:hover .icon {
  height: 800px;
  width: 800px;
  line-height: 800px;
  background-color: #ff4f8b;
  transform: translate(-50%, -45%);
}
```

`container`를 호버하는 경우 `icon` 영역이 `container` 영역보다 커지면서 확장되는 듯한 느낌을 준다. 그 과정에서 글자는 그대로 있고 영역만 커져서 `icon`이 끌어내려졌다가 올라가는 효과를 줄 수가 없다. (이부분부터는 뇌피셜에 가까운데 그래서 `line-height`로 커지는 높이의 절반까지 내려주었다가 `transform: translate`로 끌어올려준다. 사실 이 부분은 아직 잘 이해가 안된다. 의도(계산된)한 코드일까?)

```css
.container p {
  position: relative;
  top: 55px;
  opacity: 0;
  transition: all 0.5s;
  transition-delay: 0.3s;
  color: #fff;
}
```

`icon`이 `position`으로 기존 컨텍스트의 영향을 받지 않고 붕 떠져 있으니 `<p>` 태그도 `position`을 해줘야 화면에서 보이게 된다. `z-index`와도 관련이 있지만 `icon`보다 `p`가 아래에 있으므로 굳이 `z-index`를 설정해주지 않아도 `z`축에서 위에 쌓여있어서 보이게 된다. 그리고 `icon`의 호버 효과 후 위치와 `p` 태그를 겹치지 않게 하기 위해 `top`을 설정해주었다.

## 정리

- 꽤 오랜 시간 코드를 분석했지만 의도 파악이 잘 안되는 부분이 있다. 하지만 몇가지를 얻을 수 있었다. 당연하게도 트랜지션 효과로 요소가 커지는 경우 텍스트 영역을 고정된다는 것. 만약 텍스트 영역에 변화를 주고 싶다면 `line-height`나 `translate`로 할 수 있다는 것.

- 이부분은 나중에라도 다시 봐야할 듯하다.
