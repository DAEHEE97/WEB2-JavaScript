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

## console command

`var alist = document.querySelectorAll('a');`

 : `<a >`anchor 모두 노드 리스트로 반환


`console.log(alist[0])` : 노드 리스트 idx 0 값을 콘솔창에 값 나타냄


`console.log(alist[1])` : 노드 리스트 idx 1 값을 콘솔창에 값 나타냄


`console.log(alist.length)` : 노드 리스트 길이 값을 콘솔창에 값 나타냄


```
var alist = document.querySelectorAll('a');

i = 0;

while(i < alist.length):
    console.log(alist[i])
    
    alist[i].style.coler = 
    
    i = i +1

```

---

## Refactoring  - 배열과 반복문의 활용


반복문과 배열을 활용하여, css 스타일 옵션 처리


- `document.querySelector('a');`

- `document.querySelectorAll('a');` : `<a >`anchor 모두 노드 리스트로 반환

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

- self

- this


## Refactoring - Function

```.html
<!doctype html>
<html>

<head>
  <title>WEB2 - JavaScript</title>
  <meta charset="utf-8">

  <script>
  function NightDayhandler(self){
    var target = document.querySelector('body');
     
    if(self.value === 'night'){
      target.style.backgroundColor = 'black';
      target.style.color = 'white';
      self.value = 'day';

      var alist = document.querySelectorAll('a');
      var i = 0;
      while(i < alist.length){
       alist[i].style.color = 'powderblue';
       i = i + 1;
     }
    } else {
      target.style.backgroundColor = 'white';
      target.style.color = 'black';
      self.value = 'night';
      
      var alist = document.querySelectorAll('a');
      var i = 0;
      while(i < alist.length){
       alist[i].style.color = 'red';
       i = i + 1;
     }  

    }

  }
</script>
</head>

<body>
  
  <h1><a href="index.html">WEB</a></h1>

  <input id="night_day" type="button" value="night" onclick="
     NightDayhandler(this);

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

## Object (객체)

- 생성, 입력, 출력

- Property (객체 소속 변수) & Method (객체 소속 함수)
     - 둘다 `key` : method 도 클래스내 `key`로 [coworker.showall] 이므로 key 출력시 method key 도 출력됨



## Refactoring - Object


```.html

<!doctype html>
<html>

<head>
  <title>WEB2 - JavaScript</title>
  <meta charset="utf-8">

<script>

    var Links = {
      setColor:function(color){
        var alist = document.querySelectorAll('a');
        var i = 0;
        while(i < alist.length){
          alist[i].style.color = color;
          i = i + 1;
        }
      }
    }

    var Body = {
      setColor:function (color){
        document.querySelector('body').style.color = color;
      },
      setBackgroundColor:function (color){
        document.querySelector('body').style.backgroundColor = color;
      }
    }


    function NightDayhandler(self){
      var target = document.querySelector('body');
      
      if(self.value === 'night'){
        Body.setBackgroundColor('black');
        Body.setColor('white');
        self.value = 'day';

        Links.setColor('powderblue')

      } else {
        Body.setBackgroundColor('white');
        Body.setColor('black');
        self.value = 'night';
        
        Links.setColor('red')
      }
    }

</script>

</head>

  <body>
    
    <h1><a href="index.html">WEB</a></h1>

    <input id="night_day" type="button" value="night" onclick="
      NightDayhandler(this);

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

## file (파일)

중복되는 src 를 파일로 쪼개서 정리하기

1. color.js - `<script>` 제외하고 작성 후

2. `<script src="color.js"></script>`


---

## Refactoring - file

```2.html

<!doctype html>
<html>

  <head>
    <title>WEB1 - CSS</title>
    <meta charset="utf-8">
    <script src="color.js"></script>
  </head>

  <body>
    <h1><a href="index.html">WEB</a></h1>

    <input id="night_day" type="button" value="night" onclick="
    NightDayhandler(this);

    ">

    <ol>
      <li><a href="1.html">HTML</a></li>
      <li><a href="2.html">CSS</a></li>
      <li><a href="3.html">JavaScript</a></li>
    </ol>
    <h2>CSS</h2>
    <p>
      Cascading Style Sheets (CSS) is a style sheet language used for describing the presentation of a document written in a markup language. Although most often used to set the visual style of web pages and user interfaces written in HTML and XHTML, the language can be applied to any XML document, including plain XML, SVG and XUL, and is applicable to rendering in speech, or on other media. Along with HTML and JavaScript, CSS is a cornerstone technology used by most websites to create visually engaging webpages, user interfaces for web applications, and user interfaces for many mobile applications.
    </p>
  </body>

</html>

```

---

## Library & Framework



- jQuery


- CDN (Content Delivery Network): 로 직접 다운로드 없이, 서버비용을 회사측에서 대주면서, script src 로 라이브러리를 쓸수 있게 해줌

- [Google CDN jQuery](https://developers.google.com/speed/libraries?hl=ko#libraries)



```.html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.3/jquery.min.js"></script>
```

- $('a').css('color',color)


- $('body').css('color',color)


- $('body').css('backgroundColor',color)



---
