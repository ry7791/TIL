# 마크다운(Markdown)

> 일반 텍스트 형식 구문을 사용하는 마크업 언어의 일종으로 사용법이 쉽고 간결하여 빠르게 문서 정리를 할 수 있습니다. 단, 모든 HTML 마크업을 대체하지는 않습니다.



## 1. 문법

### 1.1 Header

> 헤더는 제목을 표현할 때 사용합니다. 단순히 글자의 크기를 표현하는 것이 아닌 의미론적인 중요도를 나타냅니다.

- `<h1>` 부터 `<h6>` 까지 표현 가능합니다.
- `#` 의 개수로 표현하거나 `<h1></h1>` 의 형태로 표현 가능합니다.



# h1 태그입니다.

## h2 태그입니다.

### h3 태그입니다.

#### h4 태그입니다.

##### h5태그입니다.

###### h6 태그입니다.





### 1.2 List

> 목록을 나열할 때 사용합니다. 순서가 필요한 항목과 그렇지 않은 항목으로 구분할 수 있습니다. 순서가 있는 항목 아래 순서가 없는 항목을 지정할 수 있으며 그 반대도 가능합니다.



- 순서가 없는 목록

  - `1.` 을 누르고 스페이스바를 누르면 생성할 수 있습니다.

  - `tab` 키를 눌러서 하위 항목을 생성할 수 있고 `shift + tab` 키를 눌러서 상위 항목으로 이동 할 수 있습니다.

- 순서가 있는 목록
  - `-`(하이픈)을 쓰고 스페이스바를 누르면 생성할 수 있습니다
  - `tab` 키를 눌러서 하위 항목을 생성할 수 있고 `shift + tab` 키를 눌러서 상위 항목으로 이동 할 수 있습니다.



1. 순서가 있는 항목
2. 순서가 있는 항목
   	1. 순서가 있는 하위 항목
    	2. 순서가 있는 하위 항목

- 순서가 없는 항목
- 순서가 없는 항목
  - 순서가 없는 하위 항목
  - 순서가 없는 하위 항목



### 1.3 Code Block

> 코드 블럭은 작성한 코드를 정리하거나 강조하고 싶은 부분을 나타낼 때 사용합니다. 인라인과 블럭 단위로 구분 할 수 있습니다.

- Inline
  - 인라인 블럭으로 처리하고 싶은 부분을 `(백틱) 으로 감싸줍니다.
- Block
  - `(백틱)을 3번 입력하고  Enter 를 눌러 생성합니다.



`add`  한 요소를 remote 저장소에 올리려면 `$ git push origin master` 를 터미널에 입력합니다.

``` $ git add.
$ git add .
$ git commit -m "first commit"
$ git push origin master
```



​	

## 1.4 Image

> 로컬에 있는 이미지를 삽입하거나 이미지 링크를 활용하여 이미지를 나타낼 때 사용합니다.

- `![]()` 을 작성하고 `()` 안에 이미지 주소를 입력합니다. `[]` 안에는 이미지 파일의 이름을 작성합니다.
- 로컬에 이미지파일을 저장한 경우 절대 경로가 아닌 상대 경로를 사용하여 이미지를 저장합니다.



![](data:image/png;base64,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)



### 1.5 Link

> 특정 주소로 링크를 걸 때 사용합니다.

- `[]()` 을 작성하고 `()` 안에 링크 주소를작성하고 `[]` 안에 어떤 링크 주소인지 작성합니다.



[git 공식문서](https://github.com/hongcompany/documents)

[github 공식문서](https://github.com/)



### 1.6 Table

> 표를 작성하여 요소를 구분할 수 있습니다.

- `|` (파이프) 사이에 컬럽을 작성하고 `enter` 를 입력합니다.
- 마지막 컬럼을 작성하고 뒤에 `|` 를 붙여줍니다.



| working directory | statging area | remoe repo |
| ----------------- | ------------- | ---------- |
| working tree      | index         | history    |
| working copy      | cache         | tree       |



### 1.7 기타

인용문

- `>` 을 입력하고 `enter` 키를 누릅니다

> git은 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 윈한 분산 버전 관리 시스템이다.

- 인용문 안에 인용문을 작성하면 중첩해서 사용할 수 있습니다.

> $git add.
>
> > $ git commit -m "first commit"
> >
> > > $ git push origin master



수평선

- `---` , `***`, `___` 을 입력하여 작성합니다.

___Working Directory___

---

Staging Area

---

Remote Repository

___



강조

- 이탤릭체는 해당 부분응ㄹ `*` 혹은 `_` (언더바) 로 감싸줍니다.
- 보드체는 해당 부분을 `**` 혹은 `__` (언더바 2개)로 감싸줍니다.
- 취소선은 `~~` 표시를 사용합니다.

이것은 *이탤릭체* 입니다.

이것은 __보드체__입니다.

이것은 ~~취소선~~입니다.



## 2. 과제 

> 현재의 pdf 문서를 마크다운 문법을 활용하여 `00_markdown_basic.md` 로 만들어 보세요.