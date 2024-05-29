# node.js 시작하기
node.js로 프로젝트를 만들 때는 npm init를 사용하여 새로운 프로젝트 설정을 해주는 것이 좋다.
```
$ npm init -y
```
그러면 프로젝트 설정이 적힌 package.json이 생성된다.
## 도움 되는 패키지
* express : 웹서버 프레임워크
* cors : cross-origin resource sharing 핸들링
* mongoose : mongodb connect 라이브러리
* jsonwebtoken : jwt 라이브러리
* dotenv : `.env` 환경변수 파일 제어
* cookie-parser : 쿠키 핸들링 툴
* redis : redis 클라이언트 라이브러리
* bcryptjs : 암호화 라이브러리. 패스워드 hash 값 만들 때 사용하면 좋음

설치하려는 패키지 이름을 npm install 뒤에 파라메터로 넣어준다.
```
$ npm install express cors mongoose
```
## 개발에 도움되는 툴
* nodemon

`nodemon`은 프로젝트 파일이 저장되면 프로젝트를 재시작 해준다. 그러면 수정된 코드를 바로바로 테스트 해볼 수 있다.
### 설치
```
$ npm install nodemon --save-dev
```
`--save-dev`옵션은 `pacakge.json`에 개발용도라는 것을 명시해준다.

## 개발 전 package.json 설정
아래와 같이 타입과 시작 설정을 넣어준다:
```
"type":"module",

// scripts 항목은 이미 있으며 test key를 내포하고 있다
"scripts" : {
    "start": "node index.js",
    "dev": "nodemon index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
},
```
`"type":"module"`은 `ES6`에서 도입된 `import`를 사용할 수 있게 해준다. 관련해서 자세한 사항은 [require vs import](https://inpa.tistory.com/entry/NODE-%F0%9F%93%9A-require-%E2%9A%94%EF%B8%8F-import-CommonJs%EC%99%80-ES6-%EC%B0%A8%EC%9D%B4-1)을 참고한다.
`scripts`에는 `start`와 `dev`를 추가 설정해주었다. `dev`로 실행하면 `nodemon`을 이용하여 프로그램이 실행된다:
```
$ npm run dev
```
이럴 경우 위에서 설명한 것과 같이 프로젝트의 파일이 갱신(저장)되면 `nodemon`이 프로젝트를 재시작 햐여 바로 테스트 가능하게 해준다.