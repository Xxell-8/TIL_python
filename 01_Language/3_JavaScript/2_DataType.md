# 2. Data Type

>- 자바스크립트의 모든 값은 특정한 데이터 타입을 가지는데,
>
>  - 크게 원시 타입(Primitive type)과 참조 타입(Reference type)으로 분류
>
>    1. 원시 타입
>
>       - Number, String, Boolean, undefined, null, Symbol
>
>    2. 참조 타입 👉 Objects
>
>       - 객체(Objects) 타입의 자료형
>         - 변수에 해당 객체의 참조 값이 담기고, 참조 값을 복사
>
>       - Array, Function, Object, ...



## 1. Primitive Type

> - 객체(Objects)가 아닌 기본 타입
>
> - 변수에 해당 타입의 값이 담기고, 실제 값을 복사



#### 1. Number

- 정수, 실수 구분이 없는 하나의 숫자 타입
  - 부동소수점 형식
  - cf. `NaN`(Not-A-Number)
    - 계산 불가능한 경우 반환되는 값



#### 2. String

- 텍스트 데이터를 나타내는 타입

  - 16비트 유니코드 문자의 집합

- 템플릿 리터럴 (Template Literal)

  - backtick(`) 으로 표현

  - `${ expression } 형태로 표현식 삽입

    ```javascript
    const name = 'Pepper'
    const age = 5
    const introduce = `${name} is ${age} years old.`
    ```



#### 3. undefined & null

| undefined                                                    | null                                               |
| ------------------------------------------------------------ | -------------------------------------------------- |
| 빈 값을 표현하기 위한 데이터 타입                            | 빈 값을 표현하기 위한 데이터 타입                  |
| 변수 선언 이후 직접 값을 할당하지 않으면 자동으로 `undefined`가 할당 | 개발자가 빈 값을 표현하기 위해 **의도적으로 **할당 |
| `typeof undefined` 결과 값은 `undefined`                     | `typeof null` 결과 값은 객체(`object`)             |



#### 4. Boolean

- 논리적 참/거짓을 나타내는 타입

  - true/false로 표현

- 조건문 또는 반복문에서 유용하게 사용

  - cf. 자동 형변환 규칙

    |  Data Type  |    true     |   false    |
    | :---------: | :---------: | :--------: |
    | `undefined` |      -      | 항상 거짓  |
    |   `null`    |      -      | 항상 거짓  |
    |   Number    | 나머지 경우 | 0, -0, NaN |
    |   String    | 나머지 경우 | 빈 문자열  |
    |   Object    |   항상 참   |     -      |

    

## 2. 연산자



#### 1. 할당 연산자

- 다양한 연산에 대한 단축 연산자 지원

  ```javascript
  // 1. 기본 할당
  let x = 0
  
  // 2. 사칙연산
  x += 1
  x -= 2
  x *= 3
  x /= 4
  
  // 3. Increment & Decrement 연산자
  x++ // += 1 과 동일
  x-- // -= 1 과 동일
  ```

  

#### 2. 비교 연산자

- 피연산자(숫자, 문자, Boolean 등)를 비교하고 비교의 결과값을 Boolean으로 반환하는 연산자
-  문자열은 유니코드 값을 사용하며 표준 사전순서를 기반으로 비교
  - 알파벳끼리 비교할 경우
    - 알파벳 오름차순으로 우선순위를 지님
    - 소문자가 대문자보다 우선순위를 지님



#### 3. 동등 비교 연산자 (`==`)

- 두 피연산자가 같은 값으로 평가되는지 비교 후 Boolean 값 반환
  - **암묵적 타입 변환**을 통해 타입을 일치시킨 후 같은 값인지 비교
    - 예상치 못한 결과가 발생할 수 있으므로 특별한 경우를 제외하고 사용하지 않음
  - 두 피연산자가 모두 객체일 경우, 메모리의 같은 객체를 바라보는지 판별



#### 4. 일치 비교 연산자 (`===`)

- 두 피연산자가 ① 같은 타입인지 확인하고 ② 같은 값으로 평가되는지 비교 후 Boolean 값 반환
  - **엄격한 비교**가 이뤄지며 암묵적 타입 변환이 발생하지 않음
  - 두 피연산자가 모두 객체일 경우, 메모리의 같은 객체를 바라보는지 판별



#### 5. 논리 연산자

- 세 가지 논리 연산자로 구성
  - and 연산은 `&&` 연산자
  - or 연산은 `||` 연산자
  - not 연산은 `!` 연산자



#### 6. 삼항 연산자

- 세 개의 피연산자를 사용하여 조건에 따라 값을 반환하는 연산자

  - `condition ? optionA : optionB`

    - 조건식이 참이면 A 값을, 거짓이면 B 값을 사용

  - 삼항 연산자의 결과는 변수에 할당 가능

  - 한 줄에 표기하는 것을 권장

    ```javascript
    console.log(true ? 1 : 2) // → 1
    console.log(false ? 1 : 2) // → 2
    ```

    