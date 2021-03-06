---
layout: default
title: Variable
parent: Basic
grand_parent: JavaScript
nav_order: 5
---

# JavaScript Variable
{: .no_toc .text-beta .fw-700}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Variable Basic

자바스크립트 **코드가 실행 중에 데이터를 저장하는 공간의 이름** 

&#9656; 백엔드와 다르게 데이터 타입을 지정 x

&#9656; 변수 타입이 없어서 아무 값이나 저장할 수 있다
 
### Identifiers

모든 변수는 특별한 이름(식별자)으로 식별되어야함

식별자를 만드는 규칙
{: .label .mt-2}
<div class="code-example" markdown="1">
1. 문자, 숫자, _, $을 사용할 수 있음
2. 첫번째 단어는 무조건 문자, $, _ (숫자가 오면 안됨)
3. case sensitive
4. 예약어 (reserved words)는 사용하면 안됨
</div>

### Assignment Operator

`=` 는 변수에 값을 할당하기 위해 사용되는 식별자

!Note
{: .label .label-yellow .mt-2}
<div class="code-example" markdown="1">
`==` 는 동일 유무를 판단하는 식별자
</div>

### Data Types

문자(text strings)나 숫자를 변수에 지정할 수 있음

변수에 지정할때에는 문자는 이중부호를 사용하고, 숫자는 그냥 사용하면 됨

문자 + 숫자 = 데이터 타입 문자

---

## Declaring Variables

### keyword var

변수를 선언할때 3가지 키워드가 사용됨

* var

    **대표적인 키워드**

* int

* const

### Features of Variable

* 변수를 선언한 직후에는 데이터 값이 undefined

* 한 문장에 변수 여러개 선언 가능하고 선언과 동시에 초기화 동시가능

    ```js
    var person = "John Doe", carName = "Volvo", price = 200;
    ```

* 재선언 뒤에도 값이 남아있음

    ```js
    var carName = "Volvo";
    var carName;            //still Volvo
    ```

* 산술연산자로 값을 산술할 수 있음

* Dollar Sign $을 문자로 인지함 (제이쿼리에서 많이 사용)

    달러 기호를 사용하는 것은 JavaScript에서 흔하지는 않지만 전문 프로그래머는 종종 JavaScript 라이브러리에서 주 함수의 별칭으로 사용

* Underscore (_)를 문자로 인지함 

    밑줄을 사용하는 것은 JavaScript에서 흔하지는 않지만 전문 프로그래머들 사이에서는 "개인 (숨겨진)"변수의 별칭으로 종종 사용
    
    
    
    
    
    
    
a. 전역 변수 :　함수 밖에서 선언되거나 함수 내에서 var키워드 없이 선언
b. 지역 변수 :　함수 안에서 var키워드로 선언, 선언된 함수 내에서만 사용 가능
    변수값이 같을 때 this를 사용하면 전역변수를 지역 변수가 사용되는 함수 내에서 가져올 수 있다.
        var x;
        function f(){
            var x;
            x = 1
            this.x = 100; //전역변수에 100넣기
        }
