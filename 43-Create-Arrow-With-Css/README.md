# CSS로 만드는 화살표

## 영상을 보기에 앞서 생각해보기

`border`로 만든 다음 `rotate`으로 돌리기

## 알고 있는 것 & 새롭게 알게 된 것

- 와우~ 처음에는 `border-left / border-bottom: 1px solid #fff`로 직각모양을 만든 다음 `rotate`을 돌릴줄 알았는데 이걸 그림자를 이용해서 만들거라고는 사실 상상을 못했다. 생각해보면 그림자 효과도 결국엔 번짐 부분이 없으면 선이니까 이렇게도 할 수 있는거구나라는걸 느꼈다.

- 아래 사진을 보면 `box-shadow`가 어떻게 작동되는지 이해가 될 것이다.

  ![example](https://user-images.githubusercontent.com/27342882/115040536-7f5a9980-9f0c-11eb-88b4-9528d31843ab.PNG)

  ![example1](https://user-images.githubusercontent.com/27342882/115040628-9b5e3b00-9f0c-11eb-8466-508159de68fc.PNG)

  번짐이 없는 직각 선을 만든 다음에 이를 `rotate`으로 돌려서 왼쪽과 오른쪽을 가리키는 화살표를 만들면 된다.
