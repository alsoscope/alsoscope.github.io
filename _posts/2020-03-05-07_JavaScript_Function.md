---
title: "07_Java Script Function"
date: 2020-03-05 00:00:00 -0400
categories: jekyll update
---

### 07_Java Script Function

- Java Script - 함수의 기본 문법

    - 함수의 생성과 호출

중복이 발생하면 유지보수와 가독성이 안좋고 코드의 양이 많아지기에 `함수`를 이용한다.

자바 스크립트 문법에 따라 함수 정의하기.

    f123이라는 함수를 만든다
    function f123(){
      console.log(1);
      console.log(2);
      console.log(3);
    }

    호출
    f123();

변수가 데이터의 대한 이름이라면<br>
함수는 일련의 프로그램에 대한 것.

- 함수의 입력

함수도 프로그램처럼 입력과 출력이 존재한다.
입력에 따라 다르게 동작하고, 출력에 따라 다양하게 사용할 수 있다.<br>

Math 자바 스크립트에 내장된 객체. 함수를 관리하는 디렉토리 같은 것이 객체이다.<br>
Math.round<br>
round라는 내장된 함수.

round는 입력값을 반올림을 해주는 함수

    console.log(Math.round(1.6)); //2
    console.log(Math.round(1.4)); //1

첫 번째, 두 번째 입력값을 더해주는 함수 sum()을 정의한다.

    function sum(first, second){//parameter. argument를 받아서 함수 안으로 전달하는 매개변수.
      console.log(first + second);
    }
    sum(2, 4);//argument 함수에게 입력값을 준다.
    
입력값을 sum이 받기 위해서는 sum을 호출한 부분과<br>
sum이 정의되어 있는 부분 사이에 매개변수가 있어야 한다.

입력 값 하나하나를 argument라고 한다. 인자.<br>
argument를 받아서 함수 안으로 전달하는 매개변수를 parameter라 한다.

입력값을 받아서 다르게 동작하는 변수 first, second<br>
입력값에 따라 다르게 작동한다.

- 함수의 출력

Math.round 내장 함수는 console.log 외에도 다양한 방법으로 출력 할 수 있다.<br>
하지만 sum은 sum이다.

    function sum(first, second){//parameter
      return first + second;
    }
    console.log(sum(2, 4));
    return은 값을 출력함과 동시에 함수를 종료한다.

- App 제작 - 함수를 이용해서 정리 정돈하기

중복되는 코드를 함수로 정리하기.

---

    var template=`
                <!doctype html>
                <html>
                <head>
                  <title>WEB1 - ${title}</title>
                  <meta charset="utf-8">
                </head>
                <body>
                  <h1><a href="/">WEB</a></h1>
                  ${list}
                  <h2>${title}</h2>
                  <p>${description}</p>
                </body>
                </html>
                `;

위 코드를 templateHTML 함수로 만든다.

    function templateHTML(title, list, body){
      return `
      <!doctype html>
      <html>
      <head>
        <title>WEB1 - ${title}</title>
        <meta charset="utf-8">
      </head>
      <body>
        <h1><a href="/">WEB</a></h1>
        ${list}
        ${body}
      </body>
      </html>
      `;
    }

조건문에서 활용할 때

    var template = templateHTML(title, list, `<h2>${title}</h2>${description}`);
    
---

    var list = '<ul>';
      var i = 0;
        while (i < filelist.length ) {
          list = list + `<li><a href="/?id=${filelist[i]}">${filelist[i]}</a></li>`
          i = i + 1;
        }
      list = list + '</ul>'; 

위 코드를 templateList 함수로 만든다.

    function temlplateList(filelist){
      var list = '<ul>';
      var i = 0;
        while (i < filelist.length ) {
          list = list + `<li><a href="/?id=${filelist[i]}">${filelist[i]}</a></li>`
          i = i + 1;
        }
      list = list + '</ul>';
      return list;
    }

filelist 매개변수로 값이 입력되어야 한다.

사용

    var list = templateList(filelist);

---
