# WEB2-JavaScript

- 웹 브라우저는 한번 출력되면, 바꿀수 없다.

- JavaScript는 사용자와 상호작용을 하는 언어 이다.

- vs `cmd shift L`

JavaScript가 HTML 을 제어하는 언어로, 웹 페이지를 동적으로, 다이나믹하게 만들어 준다.


---

## script 태그

- HTML 안에서 동적으로 작용

```script.html

<h1>JavaScript</h1>

<script>
  document.write(1+1);
</script>

<h1>html</h1>
1+1

```

---

## Event (이벤트)

- 웹 브라우저 위에서 일어나는 사건 


```event.html

<input type="button" value="Button" onclick="alert('hi')">

<input type="text" onchange="alert('changed')">

<input type="text" onkeydown="alert('key down!')">

```

---

## Console (콘솔)

- `F12` 콘솔창에서 script 언어 사용 가능

---

## 문자열과 숫자

---

## 변수와 대입 연산자

---

## CSS - style

### style 속성을 이용해서 CSS 사용하기

`<body id = 'target' style="background-color: black; color:white">`


### style 태그를 이용해서 CSS 사용하기

`<div> </div>` 무색무취 태그 (줄바꿈)

`<span> </span>` 무색무취 태그


### CSS 선택자

- 클래스 : `.js`


- id(identifier) : `#first`  - 최우선순위


- tag : `span`

---

```ex3.html
<!doctype html>
<html>

<head>
  <style>
    .js{
      font-weight: bold;
      color:red;
    }
    #first{
      color:green;
    }
    span{
      color:blue;
    }
  </style>
</head>

<body>
  <h1><a href="index.html">WEB</a></h1>
  <h2 style="background-color:coral;color:powderblue;">JavaScript</h2>
  <p>
    <span id="first" class="js">JavaScript</span> 
    (/ˈdʒɑːvəˌskrɪpt/[6]), often abbreviated as JS, is a high-level, dynamic, weakly typed, prototype-based, multi-paradigm, and interpreted programming language. 
    Alongside <span>HTML</span> and <span>CSS</span>, <span class="js">JavaScript</span> is one of the three core technologies of World Wide Web content production.
    It is used to make webpages interactive and provide online programs, including video games. 
    The majority of websites employ it, and all modern web browsers support it without the need for plug-ins by means of a built-in <span class="js">JavaScript</span> engine. 
    Each of the many <span class="js">JavaScript</span> engines represent a different implementation of <span class="js">JavaScript</span>, all based on the ECMAScript specification, with some engines not supporting the spec fully, and with many engines supporting additional features beyond ECMA.
  </p>
</body>

</html>

```

---

## 웹브라우저  제어 - 버튼 2 개

제어할 태그 선택하기 

- `document.querySelector('body').style ~` : body 태그 부분 변경


- `document.querySelector('#target').style ~` : id 부분 변경



```3.html

<!doctype html>
<html>

<head>
  <title>WEB1 - JavaScript</title>
  <meta charset="utf-8">
</head>

<body id = 'target' style="background-color: black; color:white">
  
  <h1><a href="index.html">WEB</a></h1>

  <input type="button" value="Night" onclick="
    document.querySelector('#target').style.backgroundColor = 'black';
    document.querySelector('#target').style.color = 'white';
  ">
  <input type="button" value="Day" onclick="
    document.querySelector('body').style.backgroundColor = 'white';
    document.querySelector('body').style.color = 'black';
  ">

  <ol>
    <li><a href="1.html">HTML</a></li>
    <li><a href="2.html">CSS</a></li>
    <li><a href="3.html">JavaScript</a></li>
  </ol>

  <h2>JavaScript</h2>
  
  <p>
    JavaScript (/ˈdʒɑːvəˌskrɪpt/[6]), often abbreviated as JS, is a high-level, dynamic, weakly typed, prototype-based, multi-paradigm, and interpreted programming language. Alongside HTML and CSS, JavaScript is one of the three core technologies of World Wide Web content production. It is used to make webpages interactive and provide online programs, including video games. The majority of websites employ it, and all modern web browsers support it without the need for plug-ins by means of a built-in JavaScript engine. Each of the many JavaScript engines represent a different implementation of JavaScript, all based on the ECMAScript specification, with some engines not supporting the spec fully, and with many engines supporting additional features beyond ECMA.
  </p>

</body>

</html>


```

---

## 조건문

---

## 비교 연산자, Boolean 데이터 타입


- `==` :`===` 

- `1 < 2` : `1&lt;2`

- `3 > 1` : `3&gt;1`

---

```ex4.html

  <body>
    <h1>Comparison operators & Boolean</h1>
    
    <h2>===</h2>

    <h3>1===1</h3>
    <script>
      document.write(1===1);
    </script>

    <h3>1===2</h3>
    <script>
      document.write(1===2);
    </script>

    <h3>1&lt;2</h3>
    <script>
      document.write(1<2);
    </script>

    <h3>3&gt;1</h3>
    <script>
      document.write(3>1);
    </script>

  </body>


```

---

## 조건문 - 버튼 1개


```.html

<!doctype html>
<html>

<head>
  <title>WEB2 - JavaScript</title>
  <meta charset="utf-8">
</head>

<body>
  
  <h1><a href="index.html">WEB</a></h1>

  <input id="night_day" type="button" value="night" onclick="
  
     if(document.querySelector('#night_day').value === 'night'){
       document.querySelector('body').style.backgroundColor = 'black';
       document.querySelector('body').style.color = 'white';

       document.querySelector('#night_day').value = 'day';
     } else {
       document.querySelector('body').style.backgroundColor = 'white';
       document.querySelector('body').style.color = 'black';
       
       document.querySelector('#night_day').value = 'night';
     }
   ">

</body>

</html>
```


---

## Refactoring - this, target 중복 제거 

```.html
<!doctype html>
<html>

<head>
  <title>WEB2 - JavaScript</title>
  <meta charset="utf-8">
</head>

<body>
  
  <h1><a href="index.html">WEB</a></h1>

  <input id="night_day" type="button" value="night" onclick="
  
     if(document.querySelector('#night_day').value === 'night'){
       document.querySelector('body').style.backgroundColor = 'black';
       document.querySelector('body').style.color = 'white';

       document.querySelector('#night_day').value = 'day';
     } 
     else {
       document.querySelector('body').style.backgroundColor = 'white';
       document.querySelector('body').style.color = 'black';
       
       document.querySelector('#night_day').value = 'night';
     }
   ">

</body>

</html>
```




---


```.html
<!doctype html>
<html>

<head>
  <title>WEB2 - JavaScript</title>
  <meta charset="utf-8">
</head>

<body>
  
  <h1><a href="index.html">WEB</a></h1>


  <input type="button" value="night" onclick="

    var target = document.querySelector('body');

     if(this.value === 'night'){
        target.style.backgroundColor = 'black';
        target.style.color = 'white';

       this.value = 'day';
     } 
     else {
        target.style.backgroundColor = 'white';
        target.style.color = 'black';
       
      this.value = 'night';
     }
   ">

</body>

</html>


```




---

## Loop (반복문)

---

## Array (배열)

---

## 배열과 반복문


---

## Refactoring  - 배열과 반복문의 활용



- `document.querySelectorAll('a');`

`<a >`anchor 모두 노드 리스트로 반환

```.html
<!doctype html>
<html>

<head>
  <title>WEB2 - JavaScript</title>
  <meta charset="utf-8">
</head>

<body>
  
  <h1><a href="index.html">WEB</a></h1>

  <input id="night_day" type="button" value="night" onclick="
     
     var target = document.querySelector('body');
     
     if(document.querySelector('#night_day').value === 'night'){
       document.querySelector('body').style.backgroundColor = 'black';
       document.querySelector('body').style.color = 'white';

       document.querySelector('#night_day').value = 'day';

       var alist = document.querySelectorAll('a');
       
       var i = 0;
       while(i < alist.length){
        alist[i].style.color = 'powderblue';
        i = i + 1;
        
      }
     } else {
       document.querySelector('body').style.backgroundColor = 'white';
       document.querySelector('body').style.color = 'black';

       document.querySelector('#night_day').value = 'night';
       
       var alist = document.querySelectorAll('a');
       
       var i = 0;
       while(i < alist.length){
        alist[i].style.color = 'red';
        i = i + 1;
        
      }  

     }
   ">

</body>

</html>
```

---

## Function (함수)


- Parameter & Argument

- return

---

## Object (객체)

- Property & Method

- method 도 클래스내 소속으로 `key` 로 출력 됨



---

## file (파일)

---

## 라이브러리 프레임워크

---

## UI vs API

---

---