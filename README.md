[CodingApple](https://online.codingapple.com/course/react-basic/)

### React 리액트 기초부터 쇼핑몰 프로젝트까지!
<details>
<summary>배울 내용</summary>

    – class 문법 없이 개발하는 2020스타일 easy-mode 리액트

    – 컴포넌트, Props, State를 이용한 웹앱 개발

    – 리액트로 HTML 모듈화해서 개발하는 법

    – JSX for 반복문, 이벤트 핸들러 등 어떻게 쓰는지 정확히 알려줌

    – 리액트 CLI로 프로젝트 생성, 관리, 빌드하는 법

    – Redux와 context API로 데이터 관리

    – Ajax 등으로 서버 API 요청하는 법 (을 배울 텐데 Ajax가 뭔지 모르니까 그것부터)

    – 라우터로 페이지 나누기

    – 리액트에서 CSS 스타일링 잘하는 법 (styled component, SASS)

    – import/destructuring/arrow function 등 필요한 ES6 문법들

    – 스마트폰에 설치 가능한 Progressive Web App으로 리액트사이트 발행하기

    – (포트폴리오 자랑용) github pages를 이용해 사이트 발행

</details>

-----

<details>
<summary>2-1</summary>
쇼핑몰 프로젝트 : 프로젝트 생성 & Bootstrap 설치

    - npm, nsx install을 사용했을 때 설치가 오래 걸린다면?
      -> 구글에 'yarn 1' 검색 후 installer 설치 + 컴퓨터 재시작
         yarn : npm보다 훨씬 빠른 라이브러리 설치 속도, 안정성을 자랑
                npm install ~~ => yarn add ~~
                npm run start => yarn start

    - 새로운 프로젝트 생성
      -> 작업 폴더를 VScode 에디터로 오픈한 뒤 터미널 오픈
         리액트 설치 명령어 입력 npx create-react-app shop
         shop이라는 폴더를 VScode 에디터로 오픈한 뒤 코딩 시작~
         터미널에서 yarn start 명령어로 미리보기 띄우기

    - CSS 쌩코딩하기 귀찮다? Bootstrap 라이브러리를 설치하자
      -> Bootstrap은 원조 라이브러리이고, 리액트에 맞게 변형한 React Bootstrap을 설치
         터미널에서 npm install react-bootstrap bootstrap 또는 yarn add react-bootstrap bootstrap
      -> 때에 따라 특정 스타일을 사용할 때 Bootstrap CSS 파일을 요구하는 경우가 있음
         사이트에 있는 CSS 파일을 index.html 파일의 <head> 태그 안에 복붙!
      -> Bootstarp 설치가 잘 되었는지 테스트 하고싶다
         1. getbootstrap.com 들어간 후 Documentation 탭으로 이동
         2. 원하는 레이아웃을 검색 ex) Button
         3. 그 중에 원하는 버튼의 HTML을 내 App.js에 복붙
         4. 미리보기에서 버튼이 뜬다면 설치 성공

</details>

-----