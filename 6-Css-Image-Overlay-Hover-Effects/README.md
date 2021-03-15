# CSS 이미지 오버레이 호버 효과

## 알고 있는 것 & 새롭게 알게 된 것

- 부모 요소를 기준으로 자식 요소를 움직이는 테크니컬을 사용했다.
```css
.parent {
  position: relative;
}

.child {
  position: absolute;
}
```
- `position: absolute`을 하는 경우 자신의 부모 요소중 가장 가까운 `position: relative`를 찾는다. 그리고 그 부모를 기준으로 움직인다. 자신이 기존에 가지고 있던 위치를 온전히 빠져나오기에 다른 요소가 영향을 받는다.
- 부모를 기준으로 자식을 가득 채울 때

방법1
```css
position: absolute;
top: 0;
right: 0;
bottom: 0;
left: 0;
```

방법2
```css
position: absolute;
top: 0;
left: 0;
width: 100%;
height: 100%;
```
- 6번 예제는 간단하다. 자식이 부모요소의 넓이와 높이를 가지게 만들어두고 숨겨두고 애니메이션 효과로 원래 위치로 되돌려놓는것이다.