# 김시온 [201840111] (JS)
---
## [6월 01일]
##### 오늘 배운 내용 요약

### 웹 브라우저의 자바스크립트

* 사용할 수 없는 코드
```
최신 버전 자바스크립트 코드             인터넷 익스플로러에서 사용해야 하는 코드

- let 키워드와 const 키워드
let variable = 273;                     var variableA = 273;
const constant = "Hello World";         var variable = "Hello World";

- 템플릿 문자열
let variable = 273;                     var variable = 273;
console.log                             console.log
(`변수의 값은 ${variable}입니다.`);      ('변수의 값은 ' + variable + '입니다.');

- 화살표 함수
const functionLiteral = () => {         const functionLiteral = function () {

};                                      };

- for of 반복문
const array = ['가', '나', '다'];       var array = ['가', '나', '다'];

for (let item of array) {               for (var item in array) { 
    console.log(item);                      console.log(array[i]);
}                                       }

- 사용할 수 없는 메소드
const array = [1, 2, 3, 4, 5];          const array = [1, 2, 3, 4, 5];

array.forEach((item, index) => {        for (var i = 0; i < array.length; i++) {
    console.log(`${item}: ${index}`);       var index = i;
});                                         var item = array[i];
                                            console.log(item + ' : ' + index);
                                        }
```

* Window 객체
```
alert(<메시지>) : 경고창을 출력합니다.
prompt(<메시지>, <임시 글자>) : 프롬프트를 출력합니다.
```

* screen 객체
```
width : 화면의 너비
height : 화면의 높이
availWidth : 실제 화면에서 사용 가능한 너비
availHeight : 실제 화면에서 사용 가능한 높이
colorDepth : 사용 가능한 색상 수
pixelDepth : 한 픽셀당 비트 수
```

* location 객체와 history 객체
```
- location 객체
herf : 문서의 URL 주소
host : 호스트 이름과 포트 번호 ex) localhost:52273
hostname : 호스트 이름 ex) localhost
port : 포트 번호 ex) 52273
pathname : 디렉터리 경로 ex) /folder/HTMLPage/html
hash : 앵커 이름(#~) ex) #test
search: 요청 매개 변수 ex) ?param=10
protocol : 프로토콜 종류 ex) http:

-location 객체의 메소드
assign(<링크>) : 매개 변수로 전달한 위치로 이동
reload() : 새로고침함
replace() : 매개 변수로 전달한 위치로 이동(뒤로 가기 불가능)

- history 객체의 메소드
forward() : 앞으로 이동
back() : 뒤로 이동
```

* navigator 객체
```
appCodeName : 웹 브라우저의 코드 이름
appName : 웹 브라우저의 이름
appVersion : 웹 브라우저의 버전
platform : 사용 중인 운영체제의 시스템 환경
userAgent : 웹 브라우저의 전체적인 정보
```


### 문서 객체 모델

* 1개의 문서 객체를 선택하는 메소드
```
document.getElementByld(아이디) : 아이디를 사용해 문서 객체를 선택
document.querySelector(선택자) : 선택자를 사용해 문서 객체를 선택
```

* 여러개의 문서 객체를 선택하는 메소드
```
document.getElementsByName(이름) : name 속성으로 여러 개의 문서 객체를 선택
document.getElementsByClassName(클래스) : class 속성으로 여러 개의 문서 객체를 선택
document.querySelectorAll : 선택자로 여러 개의 문서 객체를 선택
```

* 글자를 조작하는 속성
```
innerHTML : 문서 객체 내부의 문자를 나타냄
```

* 스타일 조작
```
스타일시트의 스타일 속성        자바스크림트의 스타일 속성
background-color                backgroundColor
border-radius                   borderRadius
border-aottom                   borderBottom
```

* 문서 객체의 속성 조작 메소드
```
setAttribute(속성 이름, 속성 값) : 속성을 지정
getAttribute(속성 이름) : 속성을 추출
```


### jQuery

* 문서 객체 개별 조작
```
- 선택된 문서 객체의 수
length : 선택된 문서 객체의 수를 구함

- 선택된 문서 객체 추출
get() : 선택한 문서 객체 중 하나를 선택

- 선택된 문서 객체 반복 적용
each() : 선택한 문서 객체에 반복을 적용

- each() 메소드의 콜백 함수
Array 객체의 forEach() 메소드           jQuery의 each() 메소드
[].forEach(function (item, index) {     $('h1').each(function (index,item) {

});                                     });
```

* 문서 객체 조작
```
- 문서 조작 메소드
text() : html 태그 내부의 문자를 조작
htmll() : html 태그 내부의 문자를 조작(HTML 태그 인식)

- 스타일 조작 메소드
css() : 스타일을 조작

- 속성 조작 메소드
attr() : 속성을 조작
```

* 문서 객체 생성
```
- 문서 객체 추가 메소드
$(<A>).prependTO(<B>) : A를 B안쪽 앞에 추가
$(<A>).appendTO(<B>) : A를 B안쪽 뒤에 추가
$(<A>).insertBefore(<B>) : A를 B 앞에 추가
$(<A>).insertAfter(<B>) : A를 B 뒤에 추가
```

* 이벤트
```
- jQuery의 이벤트 메소드
on() : 이벤트 연셜
off() : 이벤트 제거

- 키보드 이벤트
keydown() : 해당 영역에서 키보드를 눌렀을 때에 발생
keypress() : 해당 영역에서 키보드를 계속 누르고 있을 때에 발생
keyup() : 해당 영역에서 키보드를 눌렀다가 떼었을 때 발생

- 마우스 이벤트
click() : 노드(elements)를 마우스 포인터로 눌렀다가 떼었을 때에 발생
dblclick() : 노드를 더블 클릭 했을 때에 발생
hover() : mouseenter와 mouseleave 이벤트를 한번에 bind한다.
mousedown() : 노드 영역에서 마우스를 눌렀다가 떼었을 때에 발생
mouseenter() : 노드에 마우스가 진입했을 때에 발생(자식노드에서는 이벤트를 감지 못함)
mouseleave() : 마우스가 노드에서 벗어났을 때에 발생
mousemove() : 노드 영역에서 마우스를 움직였을 때에 발생
mouseout() : 노드에서 마우스 포인터가 떠났을 때에 발생
mouseover() : 노드 영역에서 마우스를 올려놓았을 때 발생 (내부노드까지 이벤트를 감지)
mouseup() : 마우스 포인터를 노드에 올려놓고 마우스 버튼을 눌렀다 떼었을 때에 발생
toggle() : click 이벤트에 핸들러를 바인딩하고 클릭할 때마다 실행될 함수들을 차례대로 실행

- 입력 양식 이벤트
blur() : 노드에서 포커스가 떠날 때에 발생
change() : 노드의 값이 변경될 때에 발생
focus() : 노드가 포커스를 획득했을 때에 발생
select() : 유저가 텍스트를 선택했을 때에 발생
submit() : 폼의 내용을 전송할 때에 발생

- 웹 브라우저 이벤트
resize() : 웹브라우저 윈도우 사이즈의 변화가 있을 때
scroll() : 스크롤이 움직일 때에 발생

- 이벤트를 한 번만 연결하는 메소드
one() : 이벤트를 한 번만 연결
```

* 애니메이션
```
- 애니메이션 메소드
animate() : 애니메이션을 적용
```


---
## [5월 25일]
##### 오늘 배운 내용 요약

### express 모듈

* express 모듈의 기본 메소드
```
express() : 서버 애플리케이션 객체를 생성
app.use() : 요청이 왔을 때 실행할 함수를 지정
app.listen() : 서버를 실행
```

* 페이지 라우팅 메소드
```
라우팅은 애플리케이션 엔드 포인트(URI)의 정의, 그리고 URI가 클라이언트 요청에 응답하는 방식

라우트 메소드는 HTTP 메소드 중 하나로부터 파생, express 클래스의 인스턴스에 연결
라우트 경로는 요청 메소드와의 조합을 통해, 요청이 이루어질 수 있는 엔드포인트를 정의
get(path, callback) : GET 요청이 발생했을 대 이벤트 리스너를 지정
post(path, callback) : POST 요청이 발생했을 대 이벤트 리스너를 지정
put(path, callback) : PUT 요청이 발생했을 대 이벤트 리스너를 지정
delete(path, callback) : DELETE 요청이 발생했을 대 이벤트 리스너를 지정
all(path, callback) : 모든 요청이 발생했을 대 이벤트 리스너를 지정
```

* response 객체
```
response객체는 서버가 클라이언트의 요청에 응답하는 정보를 담고 있는 객체
send() : 데이터 본문을 제공합니다.
status() : 상태 코드를 제공합니다.
set() : 헤더를 설정합니다.
```

* Content-Type
```
서버가 Content-Type을 제공하면 웹 브라우저는 헤더를 확인, 데이터의 형태를 확인(MIME라는 문자열로 제공)
```

* MIME 형식
```
text : 텍스트를 포함하는 모든 문서를 나타내며 이론상으로는 인간이 읽을 수 있어야 함
    (text/plain, text/html, text/css, text/javascript)
image : 모든 종류의 이미지를 나타냄, 애니메이션되는 이미지가 이미지 타입에 포함
    (image/gif, image/png, image/jpeg, image/bmp, image/webp)
audio : 모든 종류의 오디오 파일들을 나타냄
    (audio/midi, audio/mpeg, audio/webm, audio/ogg, audio/wav)
video : 모든 종류의 비디오 파일들을 나타냄
    (video/webm, video/ogg)
application : 모든 종류의 이진 데이터를 나타냄
    (application/octet-stream, application/pkcs12, application/vnd.mspowerpoint, 
    application/xhtml+xml, application/xml,  application/pdf)
```

* HTTP 상태 코드
```
1XX : 처리 중(100 Continue)
2XX : 성공(200 OK)
3XX : 리다이렉트 (300 Multiple Choices)
4XX : 클라이언트 오류 (400 Bad Request)
5XX : 서버 오류 (500 Internal Server Error)
```

* 리다이렉트
```
HTTP 리다이렉트는 3xx 상태 코드를 지닌 응답
리다이렉트 응답을 수신한 브라우저는, 제공된 새로운 URL을 사용하며 그것을 즉시 로드
대부분 리다이렉션은 사용자에게는 보이지 않는데다가, 적은 성능 저하를 일으킴
redirect() : 리다이렉트 함
```

* request 객체의 메서드
```
params : 라우팅 매개변수 추출
query : 요청 매개변수 추출
headers : 요청 헤더 추출
header() : 요청 헤더의 속성을 지정, 또는 추출
accepts(type) : 요청 헤더의 accept 속성 확인
is(type) : 요청 헤더의 Content-Type 속성 확인
```

* 주소 분석
```
프로토콜(HTTPS) : 통신에 상요되는 규칙을 의미
호스트((search.)naver.com) : 애플리케이션 서버(또는 분산 장치 등)의 위치를 의미
URL(sarch.naver) : 애플리케이션 서버 내부에서 라우트 위치를 나타냄
요청 매개 변수(?q = QA) : 추가적인 정보를 의미함
```

* 미들웨어(Middleware)
```
미들웨어는 양 쪽을 연결하여 데이터를 주고받을 수 있도록 중간에서 매개 역할을 하는 소프트웨어
트워크를 통해서 연결된 여러 개의 컴퓨터에 있는 많은 프로세스들에게 어떤 서비스를 사용할 수 있도록 연결해주는 소프트웨어

이점
 - 표준화된 인터페이스 제공 가능
 - 다양한 환경 지원, 체계가 다른 업무와 상호 연동이 가능
 - 분산된 업무를 동시에 처리 가능하여 자료의 일관성이 유지
 - 부하의 분산이 가능
```

* body-parser 미들웨어
```
HTTPpost put 요청시 request body 에 들어오는 데이터값을 읽을 수 있는 구문
파싱함과 동시에 req.body 로 입력해주어 응답 과정에서 요청에 body 프로퍼티를 새로이 쓸 수 있게 해주는 미들웨어

요청 본문의 종류
application/x-www-form-urlencoded : 웹 브라우저에서 입력 양식을 POST, PUT, DELETE 방식 등으로
전달할 때 사용하는 기본적인 요청 형식
application/json : JSON 데이터로 요청하는 방식
multipart/form-data : 대용량 파일을 전송할 때 사용하는 요청 방식
```

* RESTful 웹 서비스
```
RESTful 웹 서비스
method(route) : Explanation
GET(/user) : 모든 사용자 정보를 조회
POST(/user) : 사용자를 추가
GET(/user/:id) : 특정 사용자 정보를 조회
PUT(/user/:id) : 특정 사용자 정보를 수정
DELETE(/user/:id) : 특정 사용자 정보를 제거


RESTful 웹 서비스의 구조
method        /collection                   /collection/id
GET :       컬렉션을 조회                  컬력션의 특정 요소를 조회
POST :      컬렉션에 새로운 데이터를 추가   사용하지 않음
PUT :       컬렉션 전체를 한꺼번에 변경     컬렉션에 특정 요소를 수정
DELETE :    컬렉션 전체를 삭제             컬렉션의 특정 요소를 삭제
```



---
## [5월 18일]
##### 오늘 배운 내용 요약

### Node.js

* 문자열 자료형의 전역 변수
```
__filename : 현재 실행 중인 코드의 파일 경로를 나타냄
__dirname : 현재 실행 중인 코드의 폴더 경로를 나타냄
```

* Node에서 process 객체의 속성
```
argv : 실행 매개 변수를 나타냄 
env : 컴퓨터 환경과 관련된 정보를 나타냄 
version : Node.js 버전을 나타냄 
versions : Niode.js와 종속된 프로그램 버전을 나타냄 arch 프로세서의 아키텍처를 나타냄 
platform : 플랫폼을 나타냄
```

* Node에서 process 객체의 메서드
```
exit([exitCode =0]) : 프로그램을 종료 
memoryUsage() : 메모리 사용 정보 객체를 리턴 
uptime() : 현재 프로그램이 실행된 시간을 리턴
```

* Node에서 Event
```
대부분의 이벤트를 비동기 방식으로 처리, 비동기 방식으로 이벤트를 전달

on(event, listener) : 지정한 이벤트의 리스너를 추가
once(event, listener) : 지정한 이벤트의 리스너를 추가하지만 한 번 실행한 후에는 자동으로 리스너 제거
removeListener(event, listener) : 지정한 이벤트에 대한 리스너를 제거
```

* process 객체의 Event
```
exit : 프로세스가 종료될 때 발생
uncaughtException : 예외가 일어날 때 발생
```

* OS 모듈
```
실제 개발에서 많이 사용되는 모듈은 아니지만 운영체제와 시스템의 정보를 가져올 수 있는 모듈
CPU나 메모리, 디스크 용량이 얼마나 남았는지 확인이 필요할 때 사용
사용자가 실행하는 환경에 따라서 값이 다르게 나옴

tmpdir() : 임시 저장 폴더의 위치
endianness() : CPU의 endianness(BE 또는 LE)
hostname() : 호스트(컴퓨터) 이름
type() : 운영체제 이름
platform() : 운영체제 플랫폼
arch() : 운영체제 아키텍처
release() : 운영체제 버전
uptime() : 운영체제가 실행된 시간
loadavg() : 로드 에버리지 정보를 담은 배열
totalmem() : 시스템의 총 메모리
freemem() : 시스템의 가용 메모리
cpus() : CPU의 정보를 담은 객체. CPU의 세부 정보를 반환
networkInterfaces() : 네트워크 인터페이스 정보를 담은 배열
```

* url 모듈
```
url 정보를 객체로 가져와서 분석(parse)
url 객체를 문자열로 바꿔주는 기능(format, resolve)을 수행

parse(urlStr, [parseQueryString], [slashesDenoteHost]) : 
    url 문자열(urlStr)을 url 객체로 변환하여 리턴
format(urlObj) : url 객체를 url 문자열로 변환해 리턴
resolve(from, to) : 매개 변수를 조합하여 완전한 url 문자열을 생성해 리턴
```

* FIle System 모듈
```
파일 처리와 관련된 작업을 하는 모듈로, 보통 FileSystem을 줄여서 fs 모듈이라고 줄여 부름
동기적 읽기 방식을 사용하면 파일을 읽으면서 다른 작업을 동시에 할 수 없음
하지만 비동기적으로 읽으면 파일을 읽으면서 다른 작업도 동시에 수행할 수 있고,
파일을 다 읽으면 매개변수 callback으로 전달한 함수가 호출 가능
비동기 형식은 항상 마지막 인수가 수행 완료 시 호출할 콜백 함수로 작성되어야 함
주로 비동기적 형식을 많이 사용하지만, 
서버 시작 시 설정 파일을 읽는 작업과 같이 동기적 형식이 더 적절한 경우도 있음

([options]에는 보통 인코딩 방식을 쓰며, 웹에서는 UTF-8을 주로 사용)
fs.readFile(filename, [options], callback) : 
    filename의 파일을 [options]의 방식으로 읽은 후 callback으로 전달된 함수를 호출 (비동기적) 
fs.readFileSync(filename, [options]) : 
    filename의 파일을 [options]의 방식으로 읽은 후 문자열을 반환 (동기적)
fs.writeFile(filename, data, [options], callback) : 
    filename의 파일에 [options]의 방식으로 data 내용을 쓴 후 callback 함수를 호출 (비동기적) 
fs.writeFileSync(filename, data, [options]) : 
    filename의 파일에 [options]의 방식으로 data 내용을 씀 (동기적)

동기적 방식의 예외처리 :
    동기적 방식에서는 자바스크립트의 일반적인 예외처리 방식인 try ~ catch 구문으로 처리
비동기적 방식의 예외처리 :
    비동기적 방식에서 예외가 발생하면 callback 함수의 매개변수 err에 전달되므로 따로 try ~ catch 구문을 사용할 필요가 없음
```

* request 모듈
```
웹 요청을 쉽게 만들어 주는 모듈
Node.js가 기본적으로 제공하는 모듈이 아니라 다른 개인이 제공하는 외부 모듈

request 모듈에서 알아야 하는것 3가지 Jar, Post, Get
Jar : 쿠키를 저장하는 것, 로그인해서 정보를 가져와야 하는 필요성이 있을 때 사용
Get : 인터넷 페이지를 사용할 때에 인터넷 주소를 입력하는 것
Post : 로그인 등 입력창에 값을 넣고 데이터를 보내는 것
```

* cheerio 모듈
```
cheerio 모듈을 사용하면 HTML / XML 데이터에 대해 jQuery(제이쿼리)처럼 임의의 요소를 획득하여 조작할 수 있음
cheerio모 듈 이것을 이용한 것이 cheerio-httpchli 모듈
cheerio-httpchli 모듈은 cheerio 모듈에서 웹 페이지 취득 기능을 추가한 것

cheerio : 웹 API나, cheerio-httpchli등으로이미 취득한 데이터에서 임의의 데이터를 가져오는 경우 사용
cheerio-httpchli : 웹 페이지를 취득하는 경우 cheerio-httpchli 모듈을 사용
```

* async 모듈
```
비동기방식을 동기방식으로 쉽게 바꿔주기 위한 모듈
```


---
## [5월 11일]
##### 오늘 배운 내용 요약

### 객체

* Date 객체
```
생성자는 시간의 특정 지점을 나타내는 Date 객체를 생성
Date 객체는 1970년 1월 1일 UTC(국제표준시) 00:00으로부터 지난 시간을 밀리초로 나타내는 유닉스 타임스탬프를 사용
new Date();
new Date(value);
new Date(dateString);
new Date(year, monthIndex[, day[, hour[, minutes[, seconds[, milliseconds]]]]]);
```

* Array 객체의 메서드
```
Array 전역 객체는 배열을 생성할 때 사용하는 리스트 형태의 고수준 객체

concat() : 매개변수로 입력한 배열의 요소를 무ㅗ두 합쳐 배열을 만들어 리턴
join() : 배열 안의 모든 요소를 문자열로 만들어 리턴
pop()* : 배열의 마지막 요소를 제거하고 리턴
push()* : 배열의 마지막 부분에 새로운 요소를 추가
reverse()* : 배열의 요소 순서를 뒤집음
slice() : 배열 요소의 지정한 부분을 리턴
sort()* : 배열의 요소를 정렬
splice()* : 배열 요소의 지정한 부분을 삭제하고 삭제한 요소를 리턴
* -> 자기자신을 변화시키는 메서드
```

* JSON 객체
```
JSON 는 Douglas Crockford가 널리 퍼뜨린 Javascript 객체 문법을 따르는 문자 기반의 데이터 포맷
문자열 형태로 존재(네트워크를 통해 전송할 때 아주 유용)
```


### 예외 처리

* 예외
```
코드 실행 중에 예기치 못한 에러가 발생했을 때, 이로부터 코드의 실행 흐름을 복구할 수 있는 기능
코드 실행 중에 에러가 발생하면, 코드의 실행이 중단되어 그 시점에 실행 중이었던 작업을 완료할 수 없게 됨
코드의 실행 흐름을 원상복구할 수 있는 기능을 제공
```

* 예외 처리
```
try...catch...finally 구문을 사용하면 에러가 나더라도 코드의 실행을 지속
try 블록 바로 뒤에 finally 블록이 오면, 
finally 블록에 있는 코드는 try 블록 안에서의 에러 발생 여부와 관계 없이 무조건 실행
try 블록 내에서 return, break, continue 등으로 인해 코드의 실행 흐름이 즉시 이동될 때에도 마찬가지

에러가 안 났을 때 : try - finally
에러가 났을 때 : try - 에러 발생 - catch - finally
```

* 예외 강제 발생
```
Error 생성자와 throw 구문을 사용해서 프로그래머가 직접 에러를 발생
MyError 클래스를 통해 에러 객체를 생성할 때 에러에 대한 상세 정보를 포함시키면,
catch 블록 안에서 원상복구를 위해 이 값을 활용할 수 있음
```


---


## [05월 04일]
##### 오늘 배운 내용 요약

### 객체

* 생성자 함수 
```
객체를 생성할때 사용하는는 함수
대문자로 시작하는 이름 사용
여러개의 동일한 프로퍼티를 가지는 객체를 생성하기 위해서 필요합니다. 
```

* 프로토타입(Prototype)
```
생성자 함수로 생성한 객체들이 프로퍼티와 메서드를 공유하기 위해 사용하는 객체
함수만 갖고 있는 프로퍼티 (자바스크립트는 모든 것이 객체임으로 함수도 프로퍼티를 가질 수 있다.)
Prototype은 사용자가 만들어 주는 것이 아니고 javascript에서 자동으로 만들어 줍니다.
```

* null
```
null은 JavaScript의 원시 값 중 하나로, 어떤 값이 의도적으로 비어있음을 표현
불리언(boolean) 연산에서는 거짓으로 취급
```

* 기본 자료형과 객체 자료형
```
공통점 :
기본 자료형과 객체 자료형 모두 속성과 메소드를 사용함
차이점 :
기본 자료형은 객체가 아니므로 속성과 메소드를 추가할 수 없음
(단, 프로토타입으로 일회성 객체 자체를 바꾸면, 기본 자료형에도 속성이나 메소드를 추가할 수 있다.)
```

* Number 객체
```
Number 객체는 숫자 값으로 작업할 수 있게 해주는 래퍼(wrapper) 객체
Number 객체는 Number() 생성자를 사용하여 만듬
원시 숫자 자료형은 Number() 함수를 사용해 생성
만약 인수를 숫자로 변환할 수 없으면 NaN을 리턴
생성자로써 사용하지 않으면(new 연산자를 사용하지 않으면) Number를 사용하여 형변환을 할 수 있다.
```

* String
```
String 전역 객체는 문자열(문자의 나열)의 생성자
문자열 리터럴은 다음과 같은 형식을 사용
문자열은 String 전역 객체를 직접 사용하여 생성할 수 있다.
```


---


## [04월 27일]
##### 오늘 배운 내용 요약

### 함수

* setInterval 함수
```
일정한 시간 간격으로 작업을 수행하기 위해서 사용
clearInterval 함수를 사용하여 중지
주의할 점은 일정한 시간 간격으로 실행되는 작업이 그 시간 간격보다 오래걸릴 경우 문제가 발생할 수 있다.
```

* setTimeout 함수
```
일정한 시간 후에 작업을 한번 실행
보통 재귀적 호출을 사용하여 작업을 반복
기본적으로 setInterval 과는 달리 지정된 시간을 기다린후 작업을 수행하고, 
 다시 일정한 시간을 기다린후 작업을 수행하는 방식
지정된 시간 사이에 작업 시간이 추가 되는 것
clearTimeout() 을 사용해서 작업을 중지
```


### 객체

* 속성과 메소드(method)
```
element(요소): 배열 내부에 있는 값 하나하나
property(속성): 객체 내부에 있는 값 하나하나
객체의 다양한 자료형 
```


---


## [04월 13일]
##### 오늘 배운 내용 요약

### 함수

* 익명 함수
```
이름이 없는 함수
익명함수는 함수 자체가 '식'이기 때문에 익명함수를 변수에 할당할 수 있다.
다른 함수의 매개변수로 사용할 수도 있다.
```

* 선언적 함수
```
선언적 함수는 함수를 선언할 때 이름을 붙여주는 함수
따로 변수에 넣어주지 않고 선언할 대 붙여준 이름으로 호출
```

* 화살표 함수
```
화살표 함수는 본문이 한 줄인 함수를 작성할 때 유용
본문이 한 줄이 아니라면 다른 방법으로 화살표 함수를 작성해야 함
    1. 중괄호 없이 작성: (...args) => expression – 화살표 오른쪽에 표현식을 둠
        함수는 이 표현식을 평가하고, 평가 결과를 반환
    2. 중괄호와 함께 작성: (...args) => { body } – 본문이 여러 줄로 구성되었다면 중괄호를 사용해야 함
        다만, 이 경우는 반드시 return 지시자를 사용해 반환 값을 명기해 주어야 함
```

* 함수의 기본 형태
```
function <함수 이름>(<매개 변수>) {
    <함수 코드>
    return <리턴 값>
}
```

* 숫자 변환 함수
```
parselnt(): 문자열을 정수로 변환합니다.
parseFloat(): 문자열을 실수로 변환합니다.
```

* 타이머 함수
```
‘특정 시간 후에’ 또는 ‘특정 시간마다’ 어떤 일을 할 때 사용
시간은 밀리초로 지정. 1초를 나타내려면 1000(밀리초)을 입력
setTimeout(함수, 시간): 특정 시간 후에 함수를 실행합니다.
setInterval(함수, 시간): 특정 시간마다 함수를 실행합니다.
clearInterval(아이디): 특정 시간마다 실행하던 함수 호출을 정지합니다.
```


## [04월 06일]
##### 오늘 배운 내용 요약

### 반복문

* for in 반복문
```
for...in  문은 객체의 열거 속성을 통해 지정된 변수를 반복한다.
모든 객체에서 사용이 가능
for in 구문은 객체의 key 값에 접근할 수 있지만, value 값에 접근하는 방법은 제공하지 않는다.
```

* for of 반복문
```
for...of 문은 각각의 고유한 특성의 값을 실행할 명령과 함께 사용자 지정 반복 후크를 호출하여,
 반복 가능한 객체(배열, Map, Set, 인수 객체 등을 포함)를 통해 반복하는 루프를 만듭니다.
for of 구문을 사용하기 위해선 컬렉션 객체가 [Symbol.iterator] 속성을 가지고 있어야만 한다.
```


### 명령문

* break 키워드
```
break문은 반복문, switch문, 레이블 문과 결합한 문장을 빠져나올  때 사용한다.
    break;
    break [레이블];
```

* continue 키워드
```
continue 문은 while, do-while, for, 레이블 문을 다시 시작하기 위해 사용될 수 있다.
    continue;
    continue label;
```


---


## [03월 30일]
##### 오늘 배운 내용 요약


### 조건문

* switch 조건문
```
복수의 if 조건문은 switch문으로 바꿀 수 있다.
switch문은 하나 이상의 case문으로 구성
값과 일치하는 case문이 없다면, default문 아래의 코드가 실행(default 문이 있는 경우)
```

* 삼항 연산자
```
참/거짓에 따라 선택적으로 실행되는 조건문
조건문 ? 선택문1:선택문2 로 구성
(조건문이 참이면 선택문1을 실행하고, 조건문이 거짓이면 선택문 2를 실행)
```

* 짧은 초기화 조건문
```
||연산자를 불이 아닌 자료에 사용할 경우
    * A||B에서 A가 참이라면 A로 대치
    * A||B에서 A가 거짓이라면 B로 대치
```


### 반복문

* Array(배열)
```
여러 개의 자료를 한꺼번에 다룰 수 있는 자료형
대괄호 내부의 각 자료는 쉼표로 구분
배열에는 여러 자료형이 섞여 있을 수 있음
요소: 배열 안에 들어 있는 각 자료
```

* while 반복문
```
while (조건) { 내용 }   <-- 이렇게 구성
시작부분은 while 전에 써주고, 끝 부분은 while 내용 안에 직접 써주어야 한다. 
while문은 조건밖에 없기 때문에 몇 번 반복될 지 모를 때 주로 사용한다.
```

* for 반복문
```
for (시작; 조건; 끝) { 내용 }   <-- 이렇게 구성
for문은 반복 횟수를 정할 수 있기 때문에 몇 번 반복될 지 알 때 주로 사용한다.
```


---


## [03월 23일]
##### 오늘 배운 내용 요약


### 기본 자료형

* 템플릿 문자열
```
문자열에 변수를 포함시킬때 좀 더 직관적이고 편하게 사용하기 위한 기능
```

* 불리언(boolean)
```
참과 거짓을 표현하는 자료형
불의 값은 true 아니면 false이다.
```

* 논리 연산자

```
논리 연산자가 많이 사용되는 부분은 '범위 판단'이다.
단항 연산자:  !(NOT연산자),  ||(OR연산자),  &&(AND연산자)
```

* 변수
```
값을 저장할 때 사용하는 식별자, 변수 선언 후 변수에 값을 할당
```

* 복합 대입 연산자
```
변수에 사용할 수 있는 몇 개의 특별한 연산자가 존재
+=(기본 변수의 값에 값을 더합니다.)
-=(기본 변수의 값에 값을 빼줍니다.)
*=(기본 변수의 값에 값을 곱해줍니다.)
/=(기본 변수의 값에 값을 나눠줍니다.)
%=(기본 변수의 값에 나머지를 구합니다.)
```

* 증감 연산자
```
변수++(증감연산자가 피연산자 뒤에서 더함)
++변수(증감연산자가 피연산자 앞에서 더함)
변수--(증감연산자가 피연산자 뒤에서 뺌)
--변수(증감연산자가 피연산자 앞에서 뺌)
```


### 조건문

* if 조건문
```
볼 표현식이 true이면 내부의 문장을 실행, false이면 외부를 실행, 중첩해서 사용가능
```

* if else 조건문
```
if문에서 예외를 적을 때 else를 사용
```


### 자료형 검사

* typeof 

```
피연산자의 평가 전 자료형을 나타내는 문자열을 반환
```

* undefied

```
변수는 존재하나, 어떠한 값으로도 할당되지 않아 자료형이 정해지지(undefined) 않은 상태
```

* 강제 자료형 변환
```
Number() : 숫자로 자료형 변환
String() : 문자열로 자료형 변환
Boolean() : 불로 자료형 변환
NaN(Not a Number) : 표현 불가능한 수치형 결과를 나타내는 값
                    자기 자신과 일치하지 않는 유일한 값 (NaN == NaN 은 false)
```

* 일치 연산자
```
=== : 자료형과 값이 같은지 비교
!== : 자료형과 값이 다른지 비교
```


---


## [03월 16일]
##### 오늘 배운 내용 요약


### 이벤트
* 동기식
```
스레드(Thread): 효율적인 비동기 방식으로 장보기를 프로그래밍 언어로 구현하는 방법
```

* 비동기식
```
Node.js: 모든 모듈(라이브러리)이 처음부터 비동기 기반의 프로그램을 만들 수 있도록 설계되어 초보자도 쉽게 프로그램을 만들 수 있다.
```


### js로 할 수 있는 일
* 모바일 애플리케이션 개발
```
자바 프로그램만으로 개발가능
```

* 데스크톱 애플리케이션 개발

```
일렉트론(Electron) 모듈 : 자바스크립트 개발 전용 텍스트 에디터를 만들어 배포, 본격적으로 데스크톱 애플리케이션 개발
```

* 게임개발
```
원래 게임은 서버와 클라이언트 모두 C++로 개발했음
```

* 데이터베이스 관리
```
MongoDB: 데이터베이스를 관리할 때 자바스크립트를 활용하는 NoSQL
NoSQL: 기존의 SQL은 복잡하고 무거워 사용하기 쉬운 데이터베이스
```


### 기본용어

* 식별자
```
이름을 붙일 때 사용하는 단어, 변수와 함수 이름 등으로 사용
생성자 함수의 이름은 항상 대문자로 시작 ex)will out -> willOut
변수, 함수, 속성, 메소드의 이름은 항상 소문자로 시작 ex) will return -> willReturn
여러 단어로 된 식별자는 각 단어의 첫글자를 대문자로 함 ex) i am a boy -> iAmABoy
```

* 주석
```
//   or     /*  */
```


### 출력

* 출력 메소드
```
console 객체의 log() 메소드 사용: console.log() 메소드
```


### 기본 자료형

* 숫자
```
가장 기본적인 자료형
+   ,   -   ,   *   ,   /(몫)   ,   %(나머지)
```

* 문자열
```
문자의 집합
```

* 이스케이프 문자
```
따옴표를 문자 그대로 사용 가능
다음 문자가 특수 문자임을 알리는 백슬래시(\)를 사용
```