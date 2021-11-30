새로운 프로젝트를 하면서 `A~B` 컴포넌트에는 `Header` 와 `Footer` 컴포넌트를 적용하고 `C` 컴포넌트에는 적용하지 않기 위해 여러 방안을 시도해 보았습니다. 하지만 생각보다 구현이 쉽지 않았고 결국 지인분이 도와주셔서 해결하게 되었습니다. 도움받은 코드를 복습하고자 글을 적었습니다.

#### 기존 코드

```javascript
function App() {
  return (
    <>
      <BrowserRouter>
        <Container>
          <GlobalStyle />
          {/* <Header /> */}
          <Content>
            <Switch>
              <Route path='/' exact component={Main} />
              <Route path='/login' component={Login} />
              <Route path='/sign-up' component={SignUp} />
              <Route path='/errors/400' component={ErrorPage400} />
              <Route path='/errors/404' component={ErrorPage404} />
              <Route path='/errors/500' component={ErrorPage500} />
              <Route path='/boards/board/reference-tables/table_num' component={ScoreCard} />
              <Route path='/boards/board/schedule' component={Calendar} />
              <Route path='/board' component={Board} />
              <Route path='/company/user/info' component={CompanyInfo} />
              <Route path='/mocktest' component={MockTestPage} />
              <Route path='/interview' component={Interview} />
            </Switch>
          </Content>
          {/* <Footer /> */}
        </Container>
      </BrowserRouter>
    </>
  );
}
```

위 코드에서 `Interview` 컴포넌트에만 `Header`와 `Footer`를 적용하지 않고 싶었습니다. 이를 해결하기 위하여 아래의 두 속성을 이용하였습니다.

Switch : 안쪽에 있는 모든 컴포넌트 중 가장 처음으로 만나는 컴포넌트를 렌더링
Route : path가 같으면 prop으로 넘겨준 컴포넌트를 렌더링

위 두 속성을 이용하여 아래와 같이 코드를 작성하였습니다.

#### 수정된 코드

```javascript
const InterviewRoute = () => (
  <Content>
    <Interview />
  </Content>
);

const MainRoute = () => (
  <Content>
    <Header />
    <Switch>
      <Route path='/' exact component={Main} />
      <Route path='/login' component={Login} />
      <Route path='/sign-up' component={SignUp} />
      <Route path='/errors/400' component={ErrorPage400} />
      <Route path='/errors/404' component={ErrorPage404} />
      <Route path='/errors/500' component={ErrorPage500} />
      <Route path='/boards/board/reference-tables/table_num' component={ScoreCard} />
      <Route path='/boards/board/schedule' component={Calendar} />
      <Route path='/board' component={Board} />
      <Route path='/company/user/info' component={CompanyInfo} />
      <Route path='/mocktest' component={MockTestPage} />
      {/* <Route path='/interview' component={Interview} /> */}
    </Switch>
  </Content>
);

function App() {
  return (
    <>
      <BrowserRouter>
        <Container>
          <GlobalStyle />
          <Switch>
            <Route path='/interview' exact component={InterviewRoute} />
            <Route path='/' component={MainRoute} />
          </Switch>
        </Container>
      </BrowserRouter>
    </>
  );
}
```
