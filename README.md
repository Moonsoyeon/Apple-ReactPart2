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

<details>
<summary>2-2</summary>
평화로운 쇼핑몰 레이아웃 디자인시간

    - Bootstrap을 이용한 레이아웃 디자인
      -> 상단메뉴(Navbar) 만들기
         1. react bootstrap 공식사이트 Component 메뉴에서 navbar 검색
         2. 마음에 드는 navbear의 HTML 예제코드를 복붙
         3. import { Navbar } from 'react-bootstrap'; (딸려온 컴포넌트들도 전부 import 해줘야 함)
      -> 대문(Jumbotron) 만들기
         navbar와 똑같이 작업 ㄱㄱ 
         배경이미지를 넣으려면 
         1. <Jumbotron className="background">
         2. CSS 파일로 가서 .background{} 안에 스타일 작성
         3. src 폴더에 이미지파일을 옮겨서 ./image.jpg
      -> 상품 레이아웃 만들기
         상품 이미지를 가로로 3개, 모바일에선 세로 1열로 진열하고 싶다 (가로 3분할)
         Bootstrap 사용하기
         <div className="col-md-4">상품1</div>
         <div className="col-md-4">상품2</div>
         <div className="col-md-4">상품3</div>

</details>

<details>
<summary>2-3</summary>
코드가 넘나 길어진다면 import / export 사용해보기

    - 데이터바인딩을 하고싶은데 데이터가 너무 길다?
      -> import / export 문법으로 변수나 함수나 자료형을 다른 파일로 저장해둔 뒤에 불러오기
      -> data.js에서 App.js 이렇게 변수, 혹은 데이터를 보내려면
         1. 일단 data.js에서 원하는 데이터를 export 하고
         2. App.js에서는 data.js를 import 하면 됨
         ex)
         (data.js 파일)
         var 중요데이터 = 'Moon';
         export default 중요데이터;
         => 변수명, 함수명, 자료형 전부 배출 가능
            파일마다 export default 라는 키워드는 하나만 사용 가능
         (App.js 파일)
         import 중요데이터 from './data.js';
         => 변수명이라는 부분은 자유롭게 작성 가능
            경로 쓸 때, ./ 라는 것은 현재 경로
      -> 여러개의 변수들을 내보내고 싶으면
         ex)
         (data.js 파일)
         var name1 = 'Moon';
         var name2 = 'Kim';
         export default name1, name2;
         (App.js 파일)
         import {name1, name2} from './data.js';
         => 변수명을 자유롭게 작명이 불가능하고 export 했던 변수명 그대로 사용

    - 쇼핑몰 데이터를 state로 저장하고 싶은데 너무 길다, 다른 파일로 빼자
     -> 1. data.js 에 데이터를 저장하고
        2. App.js 에 import Data from './data.js';
        3. 사용하고 싶은 곳에서 let [shoes, shoes변경] = useState(Data);

    - 3개의 상품 데이터를 알맞는 HTML 자리에 데이터바인딩 하기
     -> ex)
        ~~~HTML잔뜩~~~
        <div className = "col-md-4">
          <img src = "https://codingapple1.github.io/shop/shoes1.jpg" width = "100%" />
          <h4>{shoes[0].title}</h4>
          <p>{shoes[0].content} & {shoes[0].price}</p>
        </div>
        ~~~shoes[1]~~~
        ~~~shoes[2]~~~

</details>

<details>
<summary>2-4</summary>
해설 : 상품목록 Component화 + 반복문

    - 상품 레이아웃 컴포넌트화 하기
      1. "col-md-4" 라는 div 박스들을 컴포넌트로 만들기
         function Goods(){
            return (
               <div classNmae="col-md-4">
                 <h4>{ shoes[0].title }</h4>
                 <p>{ shoes[0].content } & { shoes[0].price }</p>
               </div>
            )
         }
      2. App(){} 안에 필요한 위치에 <Goods /> 추가
      3. shoes라는 변수는 App 컴포넌트에 있고 Goods 컴포넌트에 없으니 props로 전송해주기
         <Goods shoes = {shoes} />

         function Goods(props){
            return (
               <div classNmae="col-md-4">
                 <h4>{ props.shoes[0].title }</h4>
                 <p>{ props.shoes[0].content } & { props.shoes[0].price }</p>
               </div>
            )
         }

    - 각각의 Goods 컴포넌트마다 다른 데이터 전송해주기
     -> shoes라는 [{}, {}, {}] 를 전부 다 전송하지 않고 하나의 {} 오브젝트만 각각 전송
        1. <Card shoes={shoes[0]} />
           <Card shoes={shoes[1]} />
           <Card shoes={shoes[2]} />
        2. <h4>{ props.shoes.title }</h4>
           <p>{ props.shoes.content } & { props.shoes.price }</p>

    - Goods 컴포넌트 반복문 돌리기
     -> shoes 라는 state 갯수만큼 돌려야하니까 shoes에 map 붙이기
        {
           shoes.map((a, i) => {
           return <Goods shoes = {shoes{i}} />
           });
        }
        => map 반복문 안에는 2개의 파라미터가 들어갈 수 있음 (a, i)
           a는 shoes라는 array에 있던 하나하나의 데이터를 의미
           i는 반복문을 돌면서 1씩 증가하는 정수 (0, 1, 2 ...)

    - 상품 이미지들 데이터바인딩 하기
     1. "<img src=”~~~/shoes1.jpg”>" 이렇게 하드코딩 되어있는 코드를
     2. <img src={ ~~~ shoes반복문돌때마다1,2,3으로변하는변수.jpg} /> 로 변경
        <img src={ 'https://codingapple1.github.io/shop/shoes' + i + '.jpg' } width="100%"/>
        => i는 map 안에 i라는 변수 (0, 1, 2 ...)
     3. i라는 변수는 App 컴포넌트가 가지고 있는 변수이기 때문에 props로 전송
        { 
            shoes.map((a,i)=>{
             return <Card shoes={shoes[i]} i={i} />
            });
        }
        <img src={ 'https://codingapple1.github.io/shop/shoes' + (props.i+1) + '.jpg' } width="100%"/>

</details>

-----