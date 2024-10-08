# html,css를 이용한 반응형 홈페이지

- html과 css를 통해 간단한 반응형 홈페이지를 만들었습니다, 원래 있는 사이트의 이미지를 보고 직접 코딩을해 똑같이 만들어보는 클론 코딩을 실시하였습니다.
- 차트는 Chart.js를 사용하였고 이모티콘은 font-awesome을 이용하였으며 기본적인 틀은 Bootstrap을 사용하였습니다.


### 특징 1
![leftbar_motion-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/18231eb5-d0d6-40f4-8727-acf731f3081b)

- 마우스를 갖다대면 왼쪽 바가 확장되며, 숨어있던 메뉴들이 오른쪽으로 이동하는 모션이 실행됩니다.
- 각 메뉴들을 누르면 해당 서비스 주소로 이동이 가능합니다.
1. 해당 메뉴의 position을 absolute로 준 뒤 left값을 마이너스를 줘 왼쪽으로 전체 크기의 3/4을 숨겼으며, 해당 바에 마우스를 올려놓으면 hover이벤트가 발생하여 left값을 다시 0으로 바꿔 나오도록 하였습니다. 또한 부드럽게 이어지도록 transition 기능을 넣어주었습니다.
2. 글자는 transition대신 keyframe을 사용하여 좀 더 유동적인 움직임을 주었습니다.

&nbsp;&nbsp;

### 특징 2
![sc-bar-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/bf028b1d-892e-4408-8e22-f8bfe3947b8c)

- 검색창을 클릭하면 검색창의 길이가 확장되는 애니메이션이 실행됩니다.
- 가독성을 위해 버튼에 마우스를 올려놓으면 색상이 변합니다.
- 검색창말고 다른 위치를 클릭하면 0.5초 이후에 검색창이 다시 수축하는 애니메이션이 실행됩니다.

1. 해당 검색창을 클릭할 시 focus 이벤트가 발생하여 해당 검색창의 크기를 늘려주었으며, 마찬가지로 transition을 통해 자연스러운 모션을 구현하였습니다.


&nbsp;&nbsp;
### 특징 3
![chart-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/5e5fb365-4190-4b07-9290-f33f8119bc8b)

- 물론 정지된 차트 그림을 집어넣거나 직접 그려서 표현할수 있었지만 Chart.js을 이용한 반응형 차트를 통해 사용자에게 상호작용이 일어나고있음을 알려주어 지루하지 않게해주었습니다.


&nbsp;&nbsp;

### 특징 4
![resize-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/bd70769d-63c8-4c85-ab5f-e666dc89d9cf)

- 반응형 웹사이트를 구현하였습니다. 해당 웹 사이트는 모든 화면 크기와 해상도에서 잘 돌아가도록 하기 위하여 특정 화면 크기에 맞게 크기와 구조가 변합니다.
- @Media screen을 이용하여 특정 px값 아래로 내려가면 여러 css 설정을 재 설정하도록 하여 구현하였습니다.

&nbsp;&nbsp;

### 그 외
![디자인](https://github.com/user-attachments/assets/4f195052-c6c3-44c4-a173-201a57874b83)

- 여러 카드 디자인들도 평범한 박스 모양을 하기보단 뒤에 shadow 기능을 주어 좀 더 입체감이 들게 하였습니다.
&nbsp;&nbsp;

![메뉴](https://github.com/user-attachments/assets/a0d06bbb-df85-4229-b979-f9beb31655f5)


- 또한 font-awesome을 이용하여 오른쪽 위에 navbar쪽을 꾸며주었습니다.


### 잡다한 문제들

1. 검색창에 focus 이벤트가 발생했을때 width 길이를 바꾸고 transition을 주었는데 저장하여도 애니메이션이 적용되지 않았다.
- 이에 20분동안 여러 부분을 수정해본결과 html 맨 위에 style.css를 부트 스트랩 코드줄보다 아래로 내리니 해결되었다.
- 아무래도 이 검색창이 부트스트랩의 navbar에 붙어있는 기능이였기때문에, style.css보다 이후에 적용되어버리면서 우선순위 문제로 크기변화가 적용되지 않았던것 같다.
```html
   <link rel="stylesheet" href="font-awesome/css/all.min.css">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    <link href="style.css" rel="stylesheet">
```
&nbsp;&nbsp;

2. 왼쪽 바가 확장될때 x축 화면이 길어짐에 따라 아래에 스크롤이 생기는 문제.
- 분명 왼쪽 메뉴바는 position이 absolute이기에 배경으로부터 공중에 띄워져있는 상태지만 left를 0으로 주게되면 화면이 약간 길어지면서 스크롤이 생기는 문제가 발생하였다.
- 여러 해결법을 찾긴했는데 제일 간단한 방법은 body 태그에 overflow-x를 hidden으로 놓아 짤리는 부분은 숨기게하여 x축 길이가 길어짐에 따른 스크롤이 생기는걸 방지하였다.

```css
body{
    overflow-x: hidden;
}
```

3. html, css 외에도 Chart.js가 문제를 보였는데, 해당 사이트를 축소시키면 마찬가지로 차트크기도 줄어들게 하였는데, 이상하게 다시 화면을 늘릴땐 차트 화면이 작아진채로 고정되는 버그가 생겼었다.
- 이에 인터넷을 검색하여 찾아본 결과, 다음과 같은 옵션을 주니 해결이 되었다.

```javascript
options: {
                responsive: true,
                onResize: handleResize,
                maintainAspectRatio: false,
                showScale: false,
                borderColor: 'purple',
                backgroundColor: 'mediumpurple',

                scales: {
                    y: {
                        beginAtZero: true
                    }
                }

            }
```
