---
title: "14_JavaScript 객체의 형식"
date: 2020-03-26 00:00:00 -0400
categories: jekyll update
---

### 14_JavaScript 객체의 형식

  - Object
  - 객체와 비슷한 형식인 Array

### Object와 Array의 차이
배열은 정보를 정리정돈할 때 순서에 따라 처리한다.<br>
배열에서 각각의 element들은 고유의 식별자가 있다. 0부터 시작한다.

객체는 순서가 없는 정보를, 순서 없이 저장하기에 좋다.<br>
숫자로 식별자를 주는 것이 아니라 이름으로 식별자를 준다.

배열은 데이터를 순서대로 넣으면 된다.<br>
객체는 데이터를 각각의 데이터마다 고유의 이름을 준다.

    //배열을 생성할 때의 literal은 대괄호이다.
    var members = ['hi', 'abc', '123'];

    //배열에 있는 데이터 가져오기
    console.log(members[1]);//abc

    //객체는 역할에 대한 정보를 담기에 적당하다.
    //객체는 표현하는 방법(Literal)이 중괄호이다.
    var roles = {
      'programmer' : 'kim',
      'designer' : 'mi',
      'manager' : 'sun'
    };
    console.log(roles.designer);//mi
