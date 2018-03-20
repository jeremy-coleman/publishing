    <HashRouter hashType='noslash'>
      <Switch>
        <Route exact={ true } path='/' component={ Hello } />
        <Route exact={ true } path='/next' component={ World } />
        <Route component={ () => <h1>204 No Content</h1> } />
      </Switch>
    </HashRouter>
  )
  
  
