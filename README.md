# **Do it! 클론 코딩 영화 평점 웹 서비스**
* Mobile-X 연구실  
2020년 3학년 1학기 하계 방학 세미나 프로젝트

---
## **목차**   
* [Ch_01 - 안녕 리액트?](#Ch_01)   
    * 01-1 클론 코딩 수업 준비하기
    * 01-2 왜 리액트일까?
    * 01-3 무엇을 클론 코딩할까?

* [Ch_02 - 리액트로 클론 코딩 시작하기](#Ch_02)
    * 02-1 슈퍼 빠른 create-react-app
    * 02-2 깃허브에 리액트 앱 업로드하기
    * 02-3 리액트 앱 살펴보고 수정하기
    * 02-4 리액트 동작 원리 알아보기

 * [Ch_03 - 리액트로 기초 개념 알아보기](#Ch_03)
    * 03-1 리액트 앱 실행 복습하기
    * 03-2 첫 번째 리액트 기초 개념: 컴포넌트
    * 03-3 두 번째 리액트 기초 개념: JSX
    * 03-4 세 번째 리액트 기초 개념: props

* [Ch_04 - 슈퍼 똑똑하게 컴포넌트 만들기](#Ch_04)
    * 04-1 비슷한 컴포넌트 여러 개 만들기
    * 04-2 map() 함수로 컴포넌트 많이 만들기
    * 04-3 음식 앱 이리저리 만지고, 고쳐보기
    * 04-4 음식 앱에 prop-types 도입하기
---
<a id = "Ch_01"></a>

## **Ch_01-안녕 리액트?**
* 클론 코딩 수업 준비하기
    1. Node.js 설치하기   
        [Node.js 설치 페이지 바로 이동](https://nodejs.org/ko/download/)

        ``` 
        > node -v  
        v12.16.1
        ```

        * Node.js란…? (Node.js 공식 사이트에서 내린 Node.js의 정의)   
            
                Node.js는 Chrome V8 JavaScript 엔진으로 빌드된 JavaScript 런타임임  
            
                Node.js는 이벤트 기반, 논 블로킹 I/O 모델을 사용해 가볍고 효율적임   
            
                Node.js의 패키지 생태계인 npm은 세계에서 가장 큰 오픈 소스 라이브러리 생태계임
            
            >(Node.js는 백엔드 영역이라는 말은 오해!!   
            Node.js를 통해서 서버도 만들수 있기 때문에 생겨난 오해라고 함)

            * Node.js가 사용되는 분야   
                * 입출력이 잦은 어플리케이션
                * 데이터 스트리밍 어플리케이션
                * 데이터를 실시간으로 다루는 어플리케이션
                * JSON API 기반 어플리케이션
                * [싱글페이지](https://junsday.tistory.com/40) 어플리케이션(SPA = Single Page Application)   
                    - 단일 페이지 어플리케이션으로 정적파일을 한번에(나눠서도 가능) 모두 다운받고 이후 사용자와의 상호작용 가운데 필요한 데이터만 서버에서 (비동기)동적으로 받게 해 트래픽의 총량을 줄이는 어플리케이션 형태.   
                    웹의 사용성(UX), 속도 향상의 이점을 가지므로 모바일 퍼스트(Mobile Firtst) 전략에 부합.    
                    웹 페이지이나 데스크탑 어플리케이션 처럼 동작하는 웹 페이지


    2. npm 설치하기
        * Node.js를 설치하면 노드 패키지 매니저(이하 npm)도 함께 설치 됨
        ``` 
        > npm -v 
        6.13.4
        ```   

        * [npm(Node Packaged Manager) 이란?](https://m.blog.naver.com/magnking/220961896609)
            * Node.js로 만들어진 모듈을 웹에서 받아서 설치하고 관리해주는 프로그램

        * 패키지 매니저의 예시들
            * Python: pip
            * Java: jpm
            * Javascript: npm

    3. npx 설치하기
        ``` 
        > npm install npx -g
        생략...
        + npx@10.2.2
        added 293 packages from 654 contributors in 11.548s
        > npx -v
        6.13.4
        ``` 
        * [npx란?](https://geonlee.tistory.com/32)
            * 자바스크립트 패키지 관리 모듈인 npm(Node Package Module)의 npm@5.2.0 버전부터 새로 추가된 도구.  
            * 따라서 npm@5.2.0 이상 버전만 깔려 있다면 npx 커맨드 사용 가능
            * npm 레지스트리의 패키지 사용 경험을 파악하기 위한 도구 -npm은 레지스트리에서 호스팅 되는 종속성을 매우 쉽게 설치하고 관리할 수 있으며, npx는 레지스트리에서 호스팅되는 CLI(Command Line Interface) 도구 및 기타 실행 파일을 쉽게 사용할 수 있음. 
                * [CLI(Command Line Interface)란?](https://medium.com/@psychet_learn/cli-cli-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90-%EB%B0%8F-%EC%82%AC%EC%9A%A9%EB%B2%95-c8d000ebc162)
                > 명령 줄 인터페이스또는 명령어 인터페이스 즉 텍스트 터미널을 통해 사용자와 컴퓨터가 상호 작용하는 방식을 말함.
            * 지금까지 일반적인 npm과 관련하여 약간의 귀찮은 과정들이 필요했던 여러가지 사항을 크게 단순화함.

    4. [VSCode 설치하기](https://code.visualstudio.com/)
        * 편리한 작업 환경을 제공해줌.

    5. git 설치하기
    ``` 
    > git --version
    git version 2.26.0.windows.1
    ``` 
    * [git이란?](https://goddaehee.tistory.com/91)
        * [git 한글 공식 메뉴얼](https://git-scm.com/book/ko/v2)
---
<a id = "Ch_02"></a>

## **Ch_02-리액트로 클론 코딩 시작하기**
1. 슈퍼 빠른 create-react-app
    * create-react-app으로 리액트 앱 만들기
        ``` 
         > npx create-react-app movie_app_2020
         Success! Create movie_app_2020 at C:\movie_app_2020
         Inside that directory, you can run several commands:
     
         npm start 
           Starts the development server.
        (생략...)
         ``` 

        * 참고: [터미널 명령어](https://m.blog.naver.com/PostView.nhn?blogId=thdbsgh3443&logNo=221286374424&proxyReferer=https:%2F%2Fwww.google.com%2F)(아무것도 모른다면 터미널 사용이 어려울 수 있음)

    * npx는 create-react-app을 다운로드 한 다음 create-react-app movie_app_2020 명령어를 실행하여 리액트 앱을 생성해줌.

    * 리액트 앱 실행하기
         ``` 
         > npm start
         Compiled succesfully!
     
         You can now view movie_app_2020 in the browser.
            Local:              http://localhost:3000
            On Your Network     http://192.168.0.192:3000
         ```    

         ![Alt text](./Image/react_start.png)   

    * 리액트 앱 종료하기
        * 리액트 앱의 종료는 명령 프롬프트(터미널)에서 Ctrl + C를 누르면 됨.

2. 깃허브에 리액트 앱 업로드 하기
    * 로컬 저장소 초기화 하기
        * 터미널에서 루트 폴더로 이동한 후 다음 명령어를 입력
            ``` 
            > git init
            Initalized empty Git repository in C:/movie_app_2020/.git/
            또는
            Reinitialized existing Git repository in C:/movie_app_2020/.git/
            ```   
    * 깃허브에 저장소 만들기
    * 깃허브 저장소에 리액트 앱 업로드하기
        ``` 
        > git remote add origin github.com/[계정 이름]/movie_app_2020.git
        ```   
    * 리액트 앱 업로드
        ``` 
        > git add .
        > git commit -m "02-2 깃허브에 리액트 앱 업로드하기"
        > git push origin master
        Enumerating objects: 23, done.
        Counting objects: 100% (23/23), done.
        (생략...)
        To https://github.com/[계정 이름]/movie_app_2020
        ```   
3. 리액트 앱 살펴보고 수정하기

4. 리액트 동작 원리 알아보기
    ![Alt text](./Image/index.png)   
    * App.js, index.js 등에 있는 파일을을 리액트가 받아와서 해석하고 만든 결과물을 index.html에 끼워 넣음.   
    (따라서 <dive id = "root"> 와 </div> 사이가 비어 있게 됨   
    즉 리액트는 index.html의 <dive id = "root"> 와 </div> 중간에 넣을 결과물을 프로젝트 폴더에 있는 파일(App.js, ...)을 해석하여 만들어 넣는 역할을 담당)    
    
    1. index.js 살펴보기

        ```js
        ReactDom.render(<App />, document.getElementById('root'));
        ```   
        > 이 코드가 App.js 파일에 작성한 코드를 index.html의 아이디가 'root'인 엘리먼트에 넣어주는 것
    
    2. index.html 수정해보기   
    * index.html 파일을 열어서 `<div id="root"></div>` 을 `<div id="potato"></div>`로 바꿔보자

        ```html
        <body>
             <noscript> You need to enable JavaScript to run this app. </noscript>
             <div id="potato"></div>
             (생략...)
        </body>
        </html>
        ```  
        > 아이디가 "potato"로 바뀌어 앱이 실행되지 않음.

        ```js
        ReactDom.render(<App />, document.getElementById('potato'));
        ```   
        > 이와 같이 수정하였을 경우에는 다시 작동 됨.

    ---    
    
<a id = "Ch_03"></a>

## **Ch_03 - 리액트로 기초 개념 알아보기**
1. 리액트 앱 실행 복습하기

2. 첫 번째 리액트 기초 개념: 컴포넌트
    1. App.js 파일로 컴포넌트의 정의 알아보기
        * App.js 파일을 열고 App() 함수와 App() 함수가 반환하는 값을 보자

        ```js
        import React from 'react';

        function App(){
            return (
                <div>
                    <h1>Hello</h1>
                </div>
            );
        }

        export default App;
        ```   
        > App() 함수가 정의되어 있고, 이 함수가 `<div><h1>Hello</h1></div>`를 반환 함.   
          이것이 바로 App 컴포넌트 정의.    
          App() 함수가 반환한 HTML이 리액트 앱 화면에 그려지는 것임.
        
    2. index.js 파일로 컴포넌트의 사용 알아보기
        ```js
        import React from 'react';
        import ReactDOM from 'react-dom';
        import App from './App';                                  //App 컴포넌트를 임포트하여 사용

        ReactDOM.render(<App />, document.getElementById('root')); //App 컴포넌트를 임포트하여 사용
        ```   
        > App 컴포넌트 생김새가 마치 HTML 태그 같으나 HTML에는 그러한 태그는 없음.       
          <App />을 ReactDOM.render() 함수의 첫번째 인자로 전달하면 App 컴포넌트가 반환하는 것들을 화면에 그릴 수 있음.    
          App 컴포넌트가 그려질 위치는 ReactDOM.render() 함수의 두 번째 인자로 전달하면 됨.   
          함수를 그대로 해석해서 **'App 컴포넌트는 아이디가 root인 엘리먼트에 그려질 것이다.'** 정도로 이해하면 됨.  
          아이디가 root인 엘리먼트는 index.html에 있음.

        ![Alt text](./Image/render.png)   

        > 리액트는 ` <App />` 과 같은 표시를 컴포넌트로 인식하고, 그 컴포넌트가 반환하는 값을 화면에 그려줌.   
        따라서 컴포넌트를 사용할 때 ` <App />` 이 아닌 ` App` 이라고 입력하면 오루가 발생함.   
        **(중요!!: 리액트는 컴포넌트와 함께 동작하고, 리액트 앱은 모두 컴포넌트로 구성됨)**
    
    3. 두 번째 리액트 기초 개념: JSX
        * 컴포넌트 = JSX(자바스크립트 + HTML 조합) 이라는 문법을 사용

        1. Potato 컴포넌트 만들기
            ```js
            import React from 'react';
            function Potato(){  //기본적인 Potato 컴포넌트 틀   
                                //(항상 컴포넌트 이름은 대문자!)
            }
            ```     
        > **주의!: 컴포넌트 이름은 항상 대문자 이어야 함!!!!!!**

        2. 다음을 참고하여 Potato 컴포넌트가 JSX를 반환하도록 해보자
             ```js
            import React from 'react';
            function Potato(){  //기본적인 Potato 컴포넌트 틀   
                                //(항상 컴포넌트 이름은 대문자!)
                return <h3> I love potato </h3>; //HTML이 아닌 JSX임
            }
            ```   
        > **주의!: return 문에 있는 것은 HTML이 아닌 JSX!!**

        3. 마지막 줄에 export default Potato; 추가
            ```js
            import React from 'react';
            function Potato(){  //기본적인 Potato 컴포넌트 틀   
                                //(항상 컴포넌트 이름은 대문자!)
                return <h3> I love potato </h3>; //HTML이 아닌 JSX임
             }

            export default Potato;
            ```   
            > export default Potato;를 추가하면 다른 파일에서 Potato 컴포넌트를 사용 가능.

        4. Potato 컴포넌트 사용하기
            ```js
            import React from 'react';
            import ReactDOM from 'react-dom';
            import App from './App';
                
            ReactDOM.render(<App /><Potato />, document.getElementById('root'));
            ```   
            > 위와 같이 수정 했을 경우에는 오류가 발생!!   
              **오류: Adjacent JSX elements must be wrapped in an enclosing tag**   
              **(인접한 JSX 요소는 반드시 하나의 태그로 감싸야 한다.)**   
              리액트는 최종적으로 단 한개의 컴포넌트를 그려야 하는데 지금은 두개의 컴포넌트를 그리려고 해서 오류가 발생.   
              **해결 방법: Potato 컴포넌트를 App 컴포넌트 안에 넣어야 한다.**
        
        5. App 컴포넌트에 Potato 컴포넌트 임포트하기
            ```js
            import React from 'react';
            import Potato from './Potato';       // ./는 현재 파일이 있는 폴더를 말함
                                                 // ../는 현재 파일의 상위 폴더를 말함
            function App(){
                return (
                    <div>
                        <h1>Hello</h1>
                        <Potato />
                    </div>
                    );
                }
            export default App;
            ```       
            ![Alt text](./Image/potato.png)

            > 크롬 개발자 도구를 실행하여 [Element] 탭을 열어 코드를 살펴보면 리액트가 `<Poatao />` 를 해석해서 `<h3> I love potato </h3>` 로 만든것을 확인 할 수 있음 
            (-> 이것이 JSX가 리액트에서 동작하는 방식임    
                    = 컴포넌트는 JSX로 만들고 JSX는 자바스크립트와 HTML을 조합한 문법)

            6. App 컴포넌트 안에 Potato 컴포넌트 만들기
                ```js
                import React from 'react';
                                                     
                function Potato(){                        //Potato 컴포넌트를 만듬.
                    return <h1> I like potato </h1>;
                }

                function App(){
                    return (
                        <div>
                            <h1>Hello</h1>
                            <Potato />                   //Potato 컴포넌트를 가져와서 사용
                        </div>
                    );
                }
                export default App;
                ```  
3. [세 번째 리액트 기초 개념: props](https://ko.reactjs.org/docs/components-and-props.html)
    * props란? 
        > 컴포넌트에서 컴포넌트로 전달하는 데이터를 말함.   
          함수의 매개 변수와 같이 함수를 효율적으로 재사용할 수 있는 것과 같음.
    
    1. 컴포넌트 여러개 사용해보기 
        ```js
        import React from 'react';

        function Movie(){                        //Movie 컴포넌트를 만듬. 정의할 때 이름과
            return <h1> I like potato </h1>;
        }

        function App(){
            return (
                <div>
                    <h1>Hello</h1>
                    <Movie />                   //컴포넌트를 사용 할 때의 이름을 모두 바꿔야함.
                </div>
            );
        }
        export default App;
        ```
        > 여기서 영화 목록을 20개 만들고 싶다면? 
          Movie 컴포넌트를 20개 복사하여 붙여 넣는 방법 (매우 비효율적이네;;)

    * 이러한 문제를 해결하고자 props가 등장!

    2. props로 컴포넌트에 데이터 전달하기
        ```js
        import React from 'react';

        function Food(){                        
            return <h1> I like potato </h1>;
        }

        function App(){
            return (
                <div>
                    <h1>Hello</h1>
                    <Food fav="kimchi" />       //fav는 favorite의 줄임말.
                </div>
            );
        }
        export default App;
        ```
        > Food 컴포넌트에 사용한 props의 이름은 fav이고, fav에 "kimchi"라는 값을 담아 Food 컴포넌트에 보냄.   
          props에는 불리언 값(true, false), 숫자, 배열과 같은 다양한 형태의 데이터를 담을 수 있음.   
          **주의!: props에 있는 데이터는 문자열인 경우를 제외하면 모두 중괄호({})로 감싸야함.**

        ```js
        (생략...)
            <Food fav="kimchi" something={true} papapapa={['hello', 1, 2, 3, 4, true]} /> 
        (생략...)
        ```   
        > 이런식으로 문자는 "" 나머지는 {}로 둘러싸여 있음.    
          여기까지의 코드를 다시 실행 시켜보면 아직까지 아무런 변화가 없음.   
        >    > Food 컴포넌트에 props 보내기만 했을 뿐 아직 사용하지 않았기 때문임.

    3. props 사용하기
        ```js
        import React from 'react';

        function Food(props){
            console.log(props)                        
            return <h1> I like potato </h1>;
        }

        function App(){
            return (
                <div>
                    <h1>Hello</h1>
                    <Food fav="kimchi"something={true} papapapa={['hello', 1, 2, 3, 4, true]} /> 
                </div>
            );
        }
        export default App;
        ```
        > 아직까지도 리액트 앱 화면에서는 아무런 변화가 없다.   
        >    > console.log()함수는 개발자 도구의 [Console]탭에만 영향을 주기 때문.

        ![ALT text](./Image/console.png)

    4. props 다시 한 번 사용하기
        ```js
        import React from 'react';

        function Food(props){              
            return <h1> I like {props.fav} </h1>;
        }

        function App(){
            return (
                <div>
                    <h1>Hello</h1>
                    <Food fav="kimchi"/> 
                </div>
            );
        }
        export default App;
        ```
        ![ALT text](./Image/kimchi.png)
        > 결과는 이렇게 나온다.   
          **Food 컴포넌트에 props에 있는 데이너 "kimchi"를 화면에 출력하려면 props.fav를 중괄호로 감싸서 사용하면 됨.**

    5. [구조 분해 할당](https://ko.javascript.info/destructuring-assignment)으로 props 사용하기
        ```js
        function Food(props){ 
            {fav} = props;             
            return <h1> I like {fav} </h1>;
        }
        ---------------------------------------------------
       function Food({fav}){              
            return <h1> I like {fav} </h1>;
        }
        ```
        > 자바스크립트 ES6의 문법 중 구조 분해 할당(destructuring-assignment)을 사용하면 점 연산자를 사용하지 않아도 됨.   
        위 두 문법 중 어느 방법이든 사용해도 된다. 

    6. 여러개의 컴포넌트에 props 사용하기
        ```js
        import React from 'react';

        function Food({fav}){              
            return <h1> I like {fav} </h1>;
        }

        function App(){
            return (
                <div>
                    <h1>Hello</h1>
                    <Food fav="kimchi"/>
                    <Food fav="ramen"/>
                    <Food fav="samgiopsal"/>
                    <Food fav="chukumi"/> 
                </div>
            );
        }
        export default App;
        ```
        ![ALT text](./Image/ramen.png)
        > Food 컴포넌트를 4개 사용하여 각 컴포넌트에 전달한 fav props를 출력.   
          각각의 fav props에는 서로 다른 값이 들어가 있어 같은 컴포넌트를 사용해도 서로 다른 문장이 출력됨.   
          **이와 같은 상황을 컴포넌트를 재사용 했다고 부름.**

    * 3장에서 배운 내용 요약
    > **(1)** 컴포넌트가 무엇인지를 알아고보 JSX를 공부했다.   
      **(2)** JSX는 단지 HTML과 자바스크립트를 조합한 문법이다.   
      **(3)** JSX를 이용해서 컴포넌트를 작성했으며 컴포넌트의 이름은 **대문자**로 시작해야함.   
      **(4)** 컴포넌트에 데이터를 전달할 때는 props를 사용하면 된다.   
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;컴포넌트에 props를 전달하면 props에 있는 데이터가 하나의 객체로 변환되어(함수)의 인자로 전달되고, &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;이걸 받아서 컴포넌트(함수)에 사용가능.    
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ES6의 구조 분해 할당을 사용하면 props를 좀 더 편리한 방법으로 사용 가능.