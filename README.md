# ethan-notes
Making my own note using ReactJS, Apollo, GraphQL, localStorage in browser.

## 강의 및 블로그
> [Offline Apollo - Nomad Coder](https://academy.nomadcoders.co/courses/423571/)

> [React와 Apollo, Parcel 기반 서비스 개발 - NAVER](https://d2.naver.com/helloworld/2838729)

* * *

## Apollo란?
<pre>
Apollo는 GraphQL 기반의 데이터를 관리하기 위한 GraphQL 기반 플랫폼이다.

GraphQL은 SQL처럼 데이터의 집합에서 특정 데이터를 불러오는 데이터 질의 언어(data query language)다. 클라이언트가 미리 선언한 데이터 구조대로 서버에 데이터를 요청하면 서버는 요청받은 구조로 데이터를 반환하는 특징이 있다. 데이터 모델에 따라 GraphQL 스키마(schema)를 선언해 두면 선언한 스키마의 하위 필드에서 원하는 필드만 HTTP 요청의 본문(body)으로 보내고 응답으로 데이터를 받을 수 있다.

글로벌 저장소(global store)와 캐시 등을 제공하는 Apollo는 Apollo Client와 Apollo Server로 나뉘어 있다. Apollo Client는 React뿐만 아니라 Angular, Vue.js, iOS, Android 등 다양한 환경에서 사용할 수 있다. Apollo Server는 Node.js 기반의 HTTP 서버로 작동한다. Apollo Client와 Apollo Server를 사용해 GraphQL 기반의 데이터를 용이하게 관리할 수 있다.

컴포넌트가 자체적으로 필요한 쿼리를 통해 랜더링을 실행하는 방식에서는 별도의 global storage가 필요하지 않다. 또한 컴포넌트 단위로 데이터를 관리하기 때문에, 데이터의 모듈화 또한 용이하다. Apollo Client 자체에도 저장소(store)가 있어서 데이터를 캐시에 저장하고 Apollo Client의 readQuery 메서드를 호출해 캐시에 저장된 데이터를 재사용할 수 있다.

Apollo를 사용하는 SSR의 장단점과 비교 자료는 상단에 걸어놓은 블로그 주소를 통해 확인할 수 있다.
</pre>

## Dependencies
> `yarn add apollo-cache-inmemory apollo-client apollo-link-state graphql graphql-tag react-apollo react-router-dom react-textarea-autosize styled-components styled-reset`

## Offline Apollo Configuration

`Apollorovider client={client}   -->  App Component`

`client+cache --> ApolloClient --> stateLink+cache --> WithClientState`

컴포넌트 별로 graphQL을 통한 데이터 통신 + state 에 대한 정보를 apollo와 cache를 통해 관리하고, 관리에 대한 정의를 client에 명시하여, 하위 컴포넌트인 App 컴포넌트에 전달하는 것으로 이해했다.( 물론 언제든지 변경 가능.... )

초기 Apollo Configuration 부분에 대한 코드 setup은 commit log를 통해 확인하자.