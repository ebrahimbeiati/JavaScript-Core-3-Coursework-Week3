# Code reading

## Question 1

Take a look at the following code:

```
1    let x = 1;
2    function f1()
3    {
4        let x = 2;
5        console.log(x);
6    }
7    console.log(x);
```

Explain why line 4 and line 6 output different numbers.
because of global scope let outside of the function is valid

## Question 2

Take a look at the following code:

```
let x = 10

function f1()
{
    console.log(x)
    let y = 20
}

console.log(f1())
console.log(y)
```

What will be the output of this code. Explain your answer in 50 words or less.
The first console.log(x) statement inside f1() prints out the value of x, which is 10. The second console.log(f1()) statement prints out undefined because that is what f1() returns. The last console.log(y) statement throws a ReferenceError because the variable y is only defined within the scope of f1().

## Question 3

Take a look at the following code:

```
const x = 9;

function f1(val) {
  val = val + 1;
  return val;
}

f1(x);
console.log(x);

const y = { x: 9 };

function f2(val) {
  val.x = val.x + 1;
  return val;
}

f2(y);
console.log(y);
```

What will be the output of this code. Explain your answer in 50 words or less.
The first console.log statement will print 10, since the value of x is not a primitive (number type) and it is being mutated directly in the scope of the f1() function, the value of x is then retained and printed.

The second console.log statement will throw an ReferenceError, since the y variable has not been defined outside of the scope of f1(). So when we try to access it outside f1(), it is not defined.

The third console.log statement will print 9, since the value of x is a primitive so when we call f1(x) a copy of the value is passed by value. Thus, when we print the global x, its value remains unchanged.

The fourth console.log statement will print 10, since the value of y is an object whose property x is mutable, the value of x is mutated directly in the scope of the f2() function and then returned, thus the value of the property x of the y object is changed from 9 to 10.
