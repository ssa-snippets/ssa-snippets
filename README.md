# <a name="top"></a> Summary SA Snippets
* [W1 D3 - Data Modeling and Classes](#w1d3)
* [W1 D5 - Data Structures and Complexity Analysis](#w1d5)
* [W2 D1 - Inheritance Patterns](#w2d1)
* [W2 D3 - Algorithms](#w2d3)
* [W2 D5 - D3](#w2d5)
* [W3 D1 - Browser apps, jQuery, and AJAX](#w3d1)
* [W3 D3 - Frameworks, MVC, and Backbone](#w3d3)
* [W3 D5 - ES6, APIs, and React](#w3d5)
* [W4 D1 - Servers and Node](#w4d1)
* [W4 D3 - Server-side Techniques](#w4dd)
* [W4 D5 - Databases](#w4d5)
* [W5 D1 - Authentication](#w5d1)
* [W5 D3 - Deployment](#w5d3)
* [W5 D5 - Angular](#w5d5)

# <a name="w1d3"></a> Data Modeling and Classes
[index](#top)


# <a name="w1d5"></a> Data Structures and Complexity Analysis
[index](#top)


# <a name="w2d1"></a> Inheritance Patterns
[index](#top)


# <a name="w2d3"></a> Algorithms
[index](#top)


# <a name="w2d5"></a> D3
[index](#top)


# <a name="w3d1"></a> Browser apps, jQuery, and AJAX
[index](#top)


# <a name="w3d3"></a> Frameworks, MVC, and Backbone
[index](#top)


# <a name="w3d5"></a> ES6, APIs, and React
[index](#top)

## Babel transpiler
Babel compilation command:
```sh
babel path/to/source --out-dir path/to/target --presets=es2015,react,stage-2 --ignore=node_modules,compiled --source-maps inline --watch
```

Required dependencies:
```js
"devDependencies": {
  "babel-preset-es2015": "",
  "babel-preset-react": "",
  "babel-preset-stage-2": ""
}
```

## ES6 class syntax:
```js
class Car extends Vehicle {
  constructor(props) {
    // omitting super => Error!
    super(props);
    this.interior = 'leather';
  }
  // , <-- wrong: no commas b/w functions in class definition
  drive() {
    // instance.drive()
    // Car.prototype.drive()
  }
  static maintenance(car) {
    // Car.maintenance()
  }
}
```

## React and JSX
Function as a component:
```js
// function that returns a component
var A = (props) => (
  <div>
    <p>Para1</p>
    <p>Para2</p>
  </div>
);
```

Class as a component:
```js
class Credentials extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      username: '',
      password: '',
      show: false
    };
  }
  handleSubmit(e) {
    e.preventDefault();
    var username = this.state.username.trim();
    var password = this.state.password.trim();
    if (!username || !password) {
      return;
    }
    var url = store.getState().loginSignupType === 'login' ? '/login' : '/signup';
    $.ajax({
      url,
      type: 'POST',
      data: {username, password},
      // data type expected back from server:
      dataType: 'text',
      success: function(favorites) {
        // perform actions with favorites
      },
      error: function(xhr, status, err) {
        // show error message;
        console.error(url, status, err.toString());
      }
    });
    store.dispatch({
      type: 'SUBMITTING_CREDENTIALS'
    });
    this.setState({author: '', text: ''});
  }
  handleUsernameChange(e) {
    this.setState({username: e.target.value});
  }
  handlePasswordChange(e) {
    this.setState({password: e.target.value});
  }
  hide() {
    this.setState({show: false});
  };
  render() {
    return (
      <div className="container">
        <form className="loginSignup" onSubmit={this.handleSubmit.bind(this)}>
          <input
            onChange={this.handleUsernameChange.bind(this)}
            placeholder="username"
            type="text"
            value={this.state.username}
          />
          <input
            onChange={this.handlePasswordChange.bind(this)}
            placeholder="password"
            type="password"
            value={this.state.password}
          />
          <input type="submit" value="Submit" />
        </form>
        <a onClick={this.hide.bind(this)}>Close</a>
      </div>
    );
  }
}
```

## Rendering basics
Components rendered automatically with `setState` or with
```js
ReactDOM.render(<App />, document.getElementById('app'));
```

## Special class methods
* `getInitialState`
* `componentDidMount`
* `componentWillUnmount`

## Special form methods
* `onChange`. [Docs](https://facebook.github.io/react/docs/forms.html#controlled-components).

# <a name="w4d1"></a> Servers and Node
[index](#top)


# <a name="w4d3"></a> Server-side Techniques
[index](#top)


# <a name="w4d5"></a> Databases
[index](#top)

## Data relationships
* **1:1**: Reference in either table to element in the other
* **1:many**: Reference in the *many* table the *one*.
* **many:many**: Two column **join table**.

Eric's example:

## SQL: Structured Query Language
Usage example:
```sql
CREATE DATABASE Company;

USE Company;

CREATE TABLE Employees (
  first varchar(15),
  last varchar(20),
  title varchar(50),
  age smallint(3),
  salary decimal(25,2)
);

SHOW databases;
SHOW tables;
DESCRIBE employees

INSERT INTO employees
  (first, last, title, age, salary)
  VALUES ('Dirk', 'Smith', 'Programmer II', 45, 75020.00);

SELECT * FROM Employees
  WHERE salary > 30000;

SELECT first, last, salary FROM Employees
  WHERE title LIKE '%Programmer%';
```

## Mongoose
Defining database connection. **Must require `db` in another file**



Schema
# <a name="w5d1"></a> Authentication
[index](#top)


# <a name="w5d3"></a> Deployment
[index](#top)


# <a name="w5d5"></a> Angular
