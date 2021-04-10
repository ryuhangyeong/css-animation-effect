# CSS 투영 글자

## 영상을 보기에 앞서 생각해보기

- 영상 보기전에 미리 실습을 해보았는데 `rotate`를 쓰는건 알겠는데 영상과 같은 느낌히 전혀 나지 않는다.

## 알고 있는 것 & 새롭게 알게 된 것

- `rotate`를 쓰는게 맞긴 한데 약간 누은(?) 느낌이 들게 하기 위해서는 `skew`를 쓰면 된다.
- `text-align: justify;` 양쪽 정렬
- `transform-origin: bottom` 효과의 기준을 정한다.
- `box-shadow`와 마찬가지로 `text-shadow`도 여러개 설정할 수 있으며 여러개를 선언하여 3D 글자를 표현할 수 있다.

- 코드 분석

  ```css
  body {
    margin: 0;
    padding: 0;
    background-color: #00b928;
  }

  .isometric {
    width: 500px;
    padding: 20px;
    box-sizing: border-box; /* border + padding + width */
    background-color: #00c32a;
    /* 가로/세로 중앙 정렬 */
    position: absolute;
    top: 50%;
    left: 50%;
    /*
        rotate(-30deg) 왼쪽으로 30deg, +는 오른쪽
        shew(30deg) 경사 변경, 오른쪽으로 누워라!
     */
    transform: translate(-50%, -50%) rotate(-30deg) skew(30deg);
    border: 1px solid rgba(0, 0, 0, 0.2);
  }

  .isometric p {
    color: #02ff75;
    font-size: 20px;
    font-family: arial;
    text-align: justify; /* 양쪽 정렬 */
  }

  .isometric h1 {
    position: relative;
    color: #fff;
    font-size: 48px;
    font-family: arial;
    text-align: justify;
    transform-origin: bottom; /* 축 변경시 기준 설정 */
    transform: skew(-50deg); /* 경사각, 누워져있으니까 오른쪽으로 땡긴다 */
    text-shadow: -1px -1px 0 #ccc, -2px -2px 0 #ccc, -3px -3px 0 #ccc;
  }

  .isometric h1::before {
    content: "isometric text";
    position: absolute;
    top: -21px;
    left: -13px;
    color: rgba(0, 0, 0, 0.1);
    font-size: 48px;
    font-family: arial;
    text-align: justify;
    transform-origin: bottom;
    transform: skew(50deg) rotateX(180deg); /* 경사각 */
    text-shadow: none;
  }
  ```

- 조금만 더 해보면 감을 잡을 수 있을거 같다. `shew`를 설정하면 어떻게 화면에서 변화가 생기는지는 사실 아직까지 머리속에서 시뮬레이션이 힘들다. 다른건 이제 알 듯하다.
- 그림자 글자는 가상 요소로 만들었다.
