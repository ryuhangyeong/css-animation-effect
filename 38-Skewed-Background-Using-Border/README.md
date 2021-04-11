# CSS 기울기 배경을 Border로

## 영상을 보기에 앞서 생각해보기

- 이전에 비슷한 UI를 만든적이 있었다. 그때는 아마 가상 요소 `::before, ::after`로 요소를 만들고 이걸 회전시킨다음에 배치를 해주었던 거 같다. 그런데 이번에는 `border`를 사용해야한다. 흐음..
- border를 이용하여 삼각형을 만드는 방법을 응용하는걸까? 이거는 이정도로 유추하고 영상을 보면서 배워나가야겠다.

## 알고 있는 것 & 새롭게 알게 된 것

- `border`에 대하여

  - `top/bottom`
    ![border-top-bottom](https://user-images.githubusercontent.com/27342882/114303877-46d14f00-9b0b-11eb-84a4-58b1f0a687c9.PNG)
  - `top/left`
    ![border-top-left](https://user-images.githubusercontent.com/27342882/114304060-2786f180-9b0c-11eb-87e0-e6fb49947fb6.PNG)
  - `top/left- transparent`
    ![border-top-left-transparent](https://user-images.githubusercontent.com/27342882/114304131-86e50180-9b0c-11eb-9443-10338c4dedeb.PNG)
  - `top/right/bottom/left
    ![border-top-right-bottom-left](https://user-images.githubusercontent.com/27342882/114304292-4e91f300-9b0d-11eb-8c70-e8f9538e0992.PNG)

  사진의 특성을 응용하여 `skew`를 표현했다.
