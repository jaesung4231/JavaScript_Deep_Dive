## 6장 데이터타입

자바스크립트(ES6)는 7개의 데이터 타입을 제공한다. 7개의 데이터 타입은 원시 타입과 객체 타입으로 분류할 수 있다.

<table style="border: 2px  ">
  <tr style="font-weight: bold">
    <td>구분</td>
    <td>데이터타입</td>
    <td>설명</td>
  </tr>
  <tr style>
    <td rowspan="6" style="border-right: 1px inset">원시 타입</td>
    <td>숫자(number) 타입</td>
    <td>숫자, 정수와 실수 구분없이 타입만 존재</td>
  </tr>
  <tr>
    <td>문자열(string) 타입</td>
    <td>문자열</td>
  </tr>
  <tr>
    <td>불리언(boolean) 타입</td>
    <td>논리적 참(true)과 거짓(false)</td>
  </tr>
  <tr>
    <td>undefined 타입</td>
    <td>var 키워드로 선언된 변수에 암묵적으로 할당되는 값</td>
  </tr>
  <tr>
    <td>null 타입</td>
    <td>값이 없다는 것을 의도적으로 명시할 때 사용하는 값</td>
  </tr>
  <tr>
    <td>심벌(symbol) 타입</td>
    <td>ES6에서 추가된 7번째 타입</td>
  </tr>
  <tr style="border-bottom: 1px inset">
    <td td rowspan="6" style="border-right: 1px inset">객체 타입</td>
    <td></td>
    <td>객체, 함수, 배열 등</td>
  </tr>
</table>

### 6.1 숫자 타입

자바스크립트는 C나 자바와 달리, 하나의 숫자 타입만 존재한다. 숫자 타입의 값은 배정밀도 64비트 부동소수점 형식을 따른다. 즉, 모든 수를 실수로 처리하며, 정수만 표현하기 위한 데이터 타입이 별도로 존재하지 않는다. 또한 자바스크립트는 2진수, 8진수, 16진수를 표현히기 위한 데이터 타입을 제공하지 않기 때문에 이들 참조하면 모두 10진수로 해석된다.

```
var integer = 10;   //정수
var double = 10.12; // 실수
var negative =-20;  // 음의 정수

var binary = 0b01000001; // 2진수
var octal = 0o101;   // 8진수
var hex = 0x41;  // 16진수

console.log(binary) // 65
console.log(octal)  // 65
console.log(hex)    // 65

console.log(binary==octal) // true
console.log(octal==hex)    // true
console.log(1==1.5)        // true

console.log(3/2)    // 1.5
console.log(10/0)    // Infinity
console.log(10/-0)   //-Infinity
console.log(1 * "String") // NaN (Not-a-number)
```

### 6.2 문자열 타입

문자열 타입은 텍스트 데이터를 나타내는 데 사용한다. 문자열은 0개 이상의 16비트 유니코드 문자의 집합으로 전 세계 대부분의 문자를 표현할 수 있다.

자바스크립트의 문자열은 원시 타입이며, 변경 불가능한 값이다.

### 6.3 템플릿 리터럴

ES6부터 템플릿 리터럴이라고 하는 새로운 문자열 표기법이 도입되었다. 템플릿 리터럴은 멀티라인 문자열, 표현식 삽입, 태그드 템플릿 등 편리한 분자열 처리 기능을 제공한다.

- [템플릿 리터럴](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Template_literals)

### 6.4 불리언 타입

불리언 타입의 값은 논리적 참, 거짓을 나타내는 true와 false뿐이다.

### 6.5 undefined 타입

undefined 타입은 undefined가 유일하다.  
undefined는 개발자가 의도적으로 할당하기 위한 값이 아니라 자바스크립트 엔진이 변수를 초기화할 때 사용하는 값이다. 때문에 개발자가 의도적으로 변수에 할당한다면 undefined의 본래 취지와 어긋날뿐더러 혼란을 줄 수 있으므로 권장하지 않는다.

변수에 값이 없다는 것을 명시하고 싶을 때는 null을 할당하는 것을 권장한다.

### 6.6 null 타입

null 타입의 값은 null이 유일하다. 프로그래밍 언어에서 null은 변수에 값이 없다는 것을 의도적으로 명시할때 사용한다.

### 6.7 심벌 타입

심벌은 ES6에서 추가된 7번째 타입으로, 변경 불가능한 원시 타입으 값이다. 심벌 값은 다른 값과 중복되지 않은 유일무이한 값이다.

심벌은 Symbol 함수를 호출해 생성한다. 이때 생성된 심벌 값은 외부에 노출되지 않으며, 다른 값과 절대 중복되지 않은 유일무이한 값이다.

```
//심볼 값 생성
var key = Symbol('key')
console.log(typeof key) // symbol

//객체 생성
var obj={}

obj[key]='value'
console.log(obj[key]); // value
```

### 6.8 객체 타입

자바스크립트는 객체 기반의 언어이며, 자바스크립트를 이루고 있는 거의 모든 것이 객체라는 것이다.

자세한 부분은 11장

### 6.9 데이터 타입의 필요성

### 6.9.1 데이터 타입에 의한 메모리 공간의 확보와 참조

값은 메모리에 저장하고 참조할 수 있어야 한다. 메모리에 값을 저장하려면 먼저 확보해야 할 메모리 공간의 크기를 결정해야 한다.
