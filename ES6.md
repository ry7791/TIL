# ES6



## var가 가진 문제

### var은 함수 스코프를 가진다.

```js
for(var i = 0; i < 10; i++){
	console.log(i);
}
console.log(i); //10
```



### 호이스팅

- var로 정의된 변수는 그 변수가 속한 스코프의 최상단으로 끌어올려진다.

```js
console.log(myVar); //undefined
var myVar = 1;
```

- 호이스팅은 직관적이지 않다.
-  기타 문제 : 정의된 변수 재정의 가능하다.



## const, let

- const, let은 블록 스코프다
- 변수가 정의된 위치와 호이스팅된 위치 사이에서 변수를 사용하려고 하면 에러가 발생한다. 이 구간을 임시적 사각지대라고 부른다.

- const는 변수를 재할당 불가능하게 만든다.
- const로 정의해도 객체의 내부 속성값은 수정 가능하다.

```js
const bar = { prop1: 'a'};
bar.prop1 = 'b';
bar.prop2 = 123;
console.log(bar) // {prop1: 'b', prop2:123}

const arr = [10,20];
arr[0] = 100;
arr.push(300);
console.log(arr); // [ 100, 20, 300]
```

