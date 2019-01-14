react
=====

### Component Life Cycle
```
  mount: constructor => componentWillMount => render => componentDidMount
  unmount: componentWillUnmount
  update: componentWillReceiveProps => shouldComponentUpdate => componentWillUpdate =>
          render => componentDidUpdate
  (if state is change then it will be start shouldComponentUpdate)
  *--------------------------------------------------------------------------------*
  | constructor ===> componentWillMount ===> render ===========> componentDidMount |
  | componentWillReceiveProps => ShouldComponentUpdate ====*                       |
  |                                      ^                 |                       |
  |                                      |                 |                       |
  | (state changed) ----------------------                 |                       |
  |                                                        |                       |
  |  componentDidUpdate <= render <= componentWillUpdate <=*                       |
  |                                                                                |
  | componentWillUnmount                                                           |
  *--------------------------------------------------------------------------------*

```

* `constructor(props)`: set base state 
* `componentWillMount()`: before mounting component (UNSAFE)<br>
    (Note: These methods are considered legacy and you should avoid them in new code)<br>
    (Note: This lifecycle was previously named componentWillMount. That name will continue to work until version 17. Use the rename-unsafe-lifecycles codemod to automatically update your components.)
* `componentDidMount()`: networking, setTimeout, setInterval
* `componentWillReceiveProps(nextProps)`: when component receive props. no rendering even if setState() is in this (UNSAFE)<br>
    (Note: These methods are considered legacy and you should avoid them in new code)<br>
    (Note: This lifecycle was previously named componentWillReceiveProps. That name will continue to work until version 17. Use the rename-unsafe-lifecycles codemod to automatically update your components.)
* `souldComponentUpdate(nextProps, nextState)`: when prop or state is changed
* `componentWillUpdate(nextProps, nextState)`: before component update (UNSAFE)<br>
    (Note: never call setState())<br>
    (Note: These methods are considered legacy and you should avoid them in new code)<br>
    (Note: This lifecycle was previously named componentWillUpdate. That name will continue to work until version 17. Use the rename-unsafe-lifecycles codemod to automatically update your components.)
* `componentDidUpdate(prevProps, prevState)`: did update
* `componentWillUnmount()`: oo
