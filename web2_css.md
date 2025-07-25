# CSS

```html
<!--
-->

<style>
  a {
    color:red;
    text-decoration: none;
  }
  .saw {
    color:gray;
  }
  .a {
    color:red;
  }
  #active {
    color:red;
  }
  h1 {
    font-size:45px;
    text-align:center;
  }
</style>

<a href="2.html" style="color:red;text-decoration:underline">CSS</a>

<a href="1.html" class="saw">HTML</a>
<a href="2.html" class="saw a" id="active">CSS</a>
<a href="3.html">JavaScript</a>

```
궁금한 점... 
bold 처리나 underline 역시 디자인의 영역이 아닌가?
css가 아닌 html에 남아있게 된 이유는 강조 역시 정보값에 해당하기 때문일까 
자잘한 단어의 강조 따위를 css로 구현하기는 어려워서 일까?

- style태그Tag / style속성Property(declaration만)
- selector선택자 ->  ,를 통해 나열 가능
- declaration효과|선언

- class="a c" -> .a(selector) / .c : grouping하는 용도
    * 태그보다 우선 순위가 높음
    * class라는 property에는 띄어쓰기로 구분된 여러 값이 들어올 수 있다
    * 하나의 tag에 여러 property가 들어올 수 있고 여러 selector를 통해 하나의 tag를 공동 제어 가능
- id="b" -> #b(selector)
    * class 보다 우선 순위가 높음
    * 유일무이, 중복 불가 -> 한 웹페이지에서 같은 id 값은 한 번만 쓰여야 함
- tag < class < id (우선 순위 +나중에 선언될 수록 우선 순위 높음)
- tag=element

```css
/*
block level element
*/
/*
inline element
*/
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      h1, a{
        border:5px solid red;
        padding:20px;
        margin:20px;
        display:block;
        width:100px;
      }
    </style>
  </head>
  <body>
    <h1>CSS</h1>
    <h1>CSS</h1>
  </body>
</html>
```

- box model
    * block level element(display:block;) : 줄바꿈 되는 태그=화면 전체를 쓰는 태그 -> 제목 태그 
    * inline element(display:inline;) : 자기 크기 만큼만 쓰는 태그
    * display:none; -> 해당 태그가 안 보이게
    * border:5px solid red; 순서 안 중요 border-width,style,color:을 줄인 것
    * html의 태그마다 부피(box)를 결정한다
 
```html
<!doctype html>
<html>
<head>
  <title>WEB - CSS</title>
  <meta charset="utf-8">
  <style>
    body{
      margin:0;
    }
    #active {
      color:red;
    }
    .saw {
      color:gray;
    }
    a {
      color:black;
      text-decoration: none;
    }
    h1 {
      font-size:45px;
      text-align: center;
      border-bottom:1px solid gray;
      margin:0;
      padding:20px;
    }
    ol{
      border-right:1px solid gray;
      width:100px;
      margin:0;
      padding:20px;
    }
  </style>
</head>
<body>
  <h1><a href="index.html">WEB</a></h1>
  <ol>
    <li><a href="1.html" class="saw">HTML</a></li>
    <li><a href="2.html" class="saw" id="active">CSS</a></li>
    <li><a href="3.html">JavaScript</a></li>
  </ol>
  <h2>CSS</h2>
  <p>
    Cascading Style Sheets (CSS)
  </p>
  </body>
  </html>
```
- grid
    * 아무런 의미와 기능이 없고 단지 디자인의 용도로만 쓰는 태그 div와 span
    * <div></div>는 block level element
    * <span></span>는 inline element
    * display: grid;
    * grid-template-columns: 150px(첫번째 열의 부피) 1fr(나머지 공간)
    * 2fr 1fr 하면 2/3와 1/3을 쓰게 됨 -> 화면 전체를 쓰게자동을로 조정되는 단위 fr
    * css에서 id 값이 abc인 태그 밑에 있는(자식) <ol> 이라는 의미 -> #abc ol{ }

 - Responsive Web: 화면의 크기에 따라서 웹페이지의 각 요소들이 반응해서 최적화 된 모양으로 바뀌게 하는 것
    * Media Query
         - @media(min-width:800px) { } -> 스크린 너비가 800px보다 크면
      
- <style> 태그를 빼고 css코드만 style.css에 저장 후 <link rel="stylesheet" href="style.css">를 사용
    * 유지보수 편리, 재사용성, 사용성 높아짐. 코드 수 감소(-> 네트워크 측면에서도 캐싱을 사용하기 때문에 트래픽 감소)

```html
@media(max-width:800px) {
  div{
    display:none;
  }
}
```
