# React



## about react

- 리액트의 장점은 가상 돔을 통해서 UI를 빠르게 업데이트한다는 점이다.
  - 가상 돔은 이전 UI 상태를 메모리에 유지해서, 변경될 UI의 최소 집합을 계산하는 기술이다.
- 리액트의 제약 사항
  - 렌더 함수는 순수 함수로 작성해야 한다.
  - 컴포넌트 상탯값은 불변 객체로 관리해야 한다.
-  코드에서 순수 함수와 불변 객체를 적극적으로 사용하면 복잡도가 낮아지고, 찾기 힘든 버그가 발생할 확률이 줄어든다. 리액트에서 이 두 제약 사항 덕분에 렌더링 성능을 크게 향상할 수 있다.
-  리액트 버전 16.8부터 훅이라는 기능이 추가되면서 함수형 컴포넌트에서도 상탯값과 생명주기 함수 코드를 작성할 수 있게 되었다.



## 바벨

- 바벨을 사용하면 최신 자바스크립트 문법을 지원하지 않는 환경에서도 최신 문법을 사용할 수 있다.
- 리액트에서는 JSX 문법을 사용하기 위해 바벨을 사용한다. 바벨이 JSX 문법으로 작성된 코드를 createElement 함수를 호출하는 코드로 변환해 준다.
  - createElement 함수보다는 JSX 문법으로 작성하는 리액트 코드가 훨씬 가독성이 좋기 때문에 JSX 사용
- 자바스크립트 파일을 변환해 주는 작업은 플러그인 단위로 이루어진다. 이러한 플러그인의 집합을 프리셋(preset)이라고 부른다.
- @babel/preset-react은 리액트 애플리케이션을 만들 때 필요한 플러그인을 모아 놓은 프리셋이다.

- 폴리필 : 실행 시점에 주입하고자 하는 객체나 함수가 현재 환경에 존재하는지 검사해서 존재하지 않는 경우에만 주입하는 게 좋다. 이렇게 기능이 존재하는지 검사해서 그 기능이 없을 때만 주입하는 것을 폴리필이라고 한다.



## 웹펙

- 웹팩은 자바스크립트로 만든 프로그램을 배포하기 좋은 형태로 묶어 주는 툴이다.
- ES6부터 모듈 시스템이 언어 차원에서 지원된다.
- ES6가 나오기 이전부터 자바스크립트의 모듈 시스템을 요구하는 개발자가 많아서 등장한 모듈 시스템이 commonJS
- 웹펙은 ESM(ES6의 모듈시스템)과 commonJS를 모두 지원한다.



## SPA

- 단일 페이지 애플리케이션은 최초 요청 시 서버에서 첫 페이지를 처리하고 이후의 라우팅은 클라이언트에서 처리하는 웹 애플리케이션이다.

### 브라우저 히스토리 API

- SPA 구현을 위해 필요한 두가지 기능
  - 자바스크립트에서 브라우저로 페이지 전환 요청을 보낼 수 있다. 단, 브라우저는 서버로 요청을 보내지 않아야 한다.
  - 브라우저의 뒤로 가기와 같은 사용자의 페이지 전환 요청을 자바스크립트에서 처리할 수 있다. 이때도 브라우저는 서버로 요청을 보내지 않아야 한다.

- react-router-dom 중 exact속성값을 입력하면 그값이 완전히 일치해야 해당 컴포넌트가 렌더링된다. 만약 Home 컴포넌트 부분에서 exact 속성값을 입력하지 않았다면 Home 컴포넌트는 항상 렌더링된다.





### <React.Fragment>

- DOM 노드에 추가하지 않고 하위의 목록을 그룹화 할 수 있다.

```react
class Table extends React.Component {
  render() {
    return (
      <table>
        <tr>
          <Columns />
        </tr>
      </table>
    );
  }
}
```

```react
class Columns extends React.Component {
  render() {
    return (
      <div>
        <td>Hello</td>
        <td>World</td>
      </div>
    );
  }
}
```

결과

html이 정상적으로 동작하기 위해 <td> 요소들을 반환해야 한다.

```react
<table>
  <tr>
    <div>
      <td>Hello</td>
      <td>World</td>
    </div>
  </tr>
</table>
```

- Fragment 사용시

```react
class Columns extends React.Component {
  render() {
    return (
      <React.Fragment>
        <td>Hello</td>
        <td>World</td>
      </React.Fragment>
    );
  }
}
```

결과

```react
<table>
  <tr>
    <td>Hello</td>
    <td>World</td>
  </tr>
</table>
```



### URL 쿼리

- 리액트 라우터 v3 에서는 URL 쿼리를 해석해서 객체로 만들어주는 기능이 자체적으로 있었는데요, 쿼리를 파싱하는 방식은 여러가지가 있어서, 개발자들이 여러가지를 방식을 사용 할 수 있도록 이 기능을 더이상 내장하지 않습니다. 따라서 URL 쿼리를 해석하는것은 우리의 몫입니다. 쿼리를 해석하기 위해선, 라이브러리를 설치해주세요. 자체적으로 구현하는 방법도 있겠지만 라이브러리를 사용하는것이 훨씬 간편합니다.

```
yarn add query-string
```



```JS
import React from 'react';
import queryString from 'query-string';

const About = ({location, match}) => {
    const query = queryString.parse(location.search);

    const detail = query.detail === 'true';

    return (
        <div>
            <h2>About {match.params.name}</h2>
            {detail && 'detail: blahblah'}
        </div>
    );
};

export default About;
```

- URL 쿼리를 만들 때 주의하실 점은, 받아오는 값들은 모두 문자열이라는 것 입니다. 알맞는 형태로 변환을 시킨다음에 비교를 하세요.