# <a name="top"></a> Summary SA Snippets
* [W1 D3 - Data Modeling and Classes](#w1d3)
* [W1 D5 - Data Structures and Complexity Analysis](#w1d5)
* [W2 D1 - Inheritance Patterns](#w2d1)
* [W2 D3 - Algorithms](#w2d3)
* [W2 D5 - D3](#w2d5)
* [W3 D1 - Browser apps, jQuery, and AJAX](#w3d1)
* [W3 D3 - Frameworks, MVC, and Backbone](#w3d3)
* [W3 D5 - ES6, APIs, and React](#w3d5)
* [W4 D1 - Servers and Node (Express)](#w4d1)
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

ES6 `class` syntax:
```js
class Car extends Vehicle {
  constructor(props) {
    // omitting super => Error!
    super(props);
    this.interior = 'leather';
  }
  // , <-- wrong
  // note: no commas b/w functions in class definition
  drive() {
    // instance.drive()
    // Car.prototype.drive()
  }
  static maintenance(car) {
    // Car.maintenance()
  }
}
```
# <a name="w4d1"></a> Servers and Node (Express)
[index](#top)

Sample index.js for creating a simple node server using Express.
Included some basic/helpful middleware you will likely use.

```
var express = require('express'); 
var morgan = require('morgan');
var bodyParser = require('body-parser');

var app = express();

//Middleware template
app.use(function(req, res, next){
  next();
});

//Server logger
app.use(morgan('dev'));

//Parses a the request to be handles as a plain object
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({extended: true}));

//Serves up your public/client folder
app.use(express.static('./client'));

//Sample routing
app.route('/')
  .get(function(req, res){
    res.send("Hello World");
  })
  .post()
  .put()
  .delete();


app.listen(8000, function(){
  console.log('server is now listening on port 8000.');
});
```

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

# <a name="w5d1"></a> Authentication
[index](#top)


# <a name="w5d3"></a> Deployment
[index](#top)


# <a name="w5d5"></a> Angular
