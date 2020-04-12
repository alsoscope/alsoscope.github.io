---
title: "16_JavaScript 객체"
date: 2020-04-02 00:00:00 -0400
categories: jekyll update
---

### 16_JavaScript - 객체

#### 데이터와 처리 방법을 담는 그릇으로서의 객체

JS에서의 함수는 값이기도 하다. 그렇기에 배열과 객체에 담을 수 있다.

값으로서의 함수를 배열에 담는 경우는 많지 않다.<br>
대신 객체에 많이 담는다. 담아놓은 함수를 이름으로 꺼낼 수 있기에.

자바 스크립트에서는 함수가 값이라는 특성을 이용하면,<br>
함수를 함수가 사용하고 있는 데이터들이 그룹핑 되어있는 객체에 멤버로서 추가할 수 있다.<br>
__이름이 없는 함수로 추가한다.__

      //기존의 코드
      var o = {
        v1:'v1',
        v2:'v2'
      }

      function f1(){
        console.log(o.v1);
      }

      function f2(){
        console.log(o.v2);
      }

      f1();
      f2();
      
---

      //수정
      var o = {
        v1:'v1',
        v2:'v2',
        f1:function(){
          console.log(o.v1);
        },
        f2:function(){
            console.log(o.v2);
        }
      }

      o.f1();
      o.f2();

o라고 하는 하나의 객체 안에 서로 연관된 값들과 이를 처리하는 함수들이 그룹핑 되어 있다.

      console.log(o.v1);
      //매번 객체명을 명시하면 함수를 담고있는 객체명이 변경됐을 때 문제가 생긴다.

함수가 객체 안에서 사용될 때 자신이 속해있는 객체를 참조할 수 있는 어떤 약속이 존재한다.<br>
**this** 라는 약속된 키워드를 사용.

만든 객체가 어떠한 이름에 변수에 담겨있든, 언제나 함수 내에서 this 라는 약속된 값을 통해서<br>
함수가 속해있는 객체를 참조할 수 있다.

      console.log(this.v1);

함수는 값이다. 객체는 값을 저장한다. 이런 특성을 이용해서 서로 연관된 데이터와 연관된 처리법을<br>
담고 있는 함수를 그룹핑 하는 것을 통해서 코드의 복잡성을 낮출 수 있다.

객체 지향을 바라보는 이미지 중의 하나.

객체라는 건 결국 코드가 복잡해짐에 따라 코드를 정리정돈해서 코드의 복잡성을 낮추는<br>
기본적인 기능부터 출발한다.