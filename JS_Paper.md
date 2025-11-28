# JavaScript Output-Based Questions - Paper 1

## Questions

### Question 1
```javascript
var x = 1;
function foo() {
  console.log(x);
  var x = 2;
  console.log(x);
}
foo();
```

**Your Answer:**
```
First console.log: _________________
Second console.log: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 2
```javascript
console.log(typeof typeof 1);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 3
```javascript
const arr = [1, 2, 3];
arr[10] = 99;
console.log(arr.length);
console.log(arr[5]);
```

**Your Answer:**
```
arr.length: _________________
arr[5]: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 4
```javascript
console.log(0.1 + 0.2);
console.log(0.1 + 0.2 === 0.3);
```

**Your Answer:**
```
0.1 + 0.2: _________________
0.1 + 0.2 === 0.3: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 5
```javascript
function foo() {
  return {
    bar: "hello"
  };
}
function baz() {
  return
  {
    bar: "hello"
  }
}
console.log(foo());
console.log(baz());
```

**Your Answer:**
```
foo(): _________________
baz(): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 6
```javascript
const obj = {
  a: 1,
  b: 2,
  a: 3
};
console.log(obj.a);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 7
```javascript
console.log([1, 2, 3] + [4, 5, 6]);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 8
```javascript
let a = {}, b = { key: 'b' }, c = { key: 'c' };
a[b] = 123;
a[c] = 456;
console.log(a[b]);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 9
```javascript
console.log([] == ![]);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 10
```javascript
console.log('5' + 3);
console.log('5' - 3);
```

**Your Answer:**
```
'5' + 3: _________________
'5' - 3: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 11
```javascript
const length = 4;
const numbers = [];
for (var i = 0; i < length; i++) {
  numbers.push(i + 1);
}
numbers.forEach(function(num) {
  setTimeout(function() {
    console.log(num);
  }, 0);
});
```

**Your Answer:**
```
Output (in order): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 12
```javascript
function Parent() {
  this.a = 1;
}
Parent.prototype.b = 2;
const child = new Parent();
console.log(child.a);
console.log(child.b);
delete child.a;
delete child.b;
console.log(child.a);
console.log(child.b);
```

**Your Answer:**
```
First child.a: _________________
First child.b: _________________
Second child.a: _________________
Second child.b: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 13
```javascript
console.log(1 < 2 < 3);
console.log(3 > 2 > 1);
```

**Your Answer:**
```
1 < 2 < 3: _________________
3 > 2 > 1: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 14
```javascript
const obj1 = { key: 'value' };
const obj2 = obj1;
obj2.key = 'newValue';
console.log(obj1.key);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 15
```javascript
console.log(typeof NaN);
console.log(NaN === NaN);
console.log(Object.is(NaN, NaN));
```

**Your Answer:**
```
typeof NaN: _________________
NaN === NaN: _________________
Object.is(NaN, NaN): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 16
```javascript
function foo() {
  let x = y = 10;
}
foo();
console.log(typeof x);
console.log(typeof y);
```

**Your Answer:**
```
typeof x: _________________
typeof y: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 17
```javascript
const arr1 = [1, 2, 3];
const arr2 = [1, 2, 3];
console.log(arr1 == arr2);
console.log(arr1 === arr2);
```

**Your Answer:**
```
arr1 == arr2: _________________
arr1 === arr2: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 18
```javascript
function sum(a, b) {
  return a + b;
}
console.log(sum(1, '2', 3));
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 19
```javascript
const person = {
  name: 'John',
  age: 30
};
for (let key in person) {
  console.log(key);
}
```

**Your Answer:**
```
Output (in order): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 20
```javascript
console.log(+'42');
console.log(typeof +'42');
console.log(!'');
console.log(typeof !'');
```

**Your Answer:**
```
+'42': _________________
typeof +'42': _________________
!'': _________________
typeof !'': _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 21
```javascript
const arr = [1, 2, 3, 4, 5];
arr.length = 2;
console.log(arr);
console.log(arr[3]);
```

**Your Answer:**
```
arr: _________________
arr[3]: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 22
```javascript
function outer() {
  var x = 10;
  return function inner() {
    console.log(x);
    var x = 20;
    console.log(x);
  }
}
outer()();
```

**Your Answer:**
```
First console.log: _________________
Second console.log: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 23
```javascript
console.log([...'Hello']);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 24
```javascript
const obj = { a: 1, b: 2, c: 3 };
const { a, ...rest } = obj;
console.log(a);
console.log(rest);
```

**Your Answer:**
```
a: _________________
rest: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 25
```javascript
console.log(null == undefined);
console.log(null === undefined);
console.log(null == 0);
console.log(null === 0);
```

**Your Answer:**
```
null == undefined: _________________
null === undefined: _________________
null == 0: _________________
null === 0: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 26
```javascript
const arr = [1, 2, 3, 4, 5];
delete arr[2];
console.log(arr);
console.log(arr.length);
console.log(arr[2]);
```

**Your Answer:**
```
arr: _________________
arr.length: _________________
arr[2]: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 27
```javascript
function test() {
  console.log(a);
  console.log(foo());
  var a = 1;
  function foo() {
    return 2;
  }
}
test();
```

**Your Answer:**
```
First console.log: _________________
Second console.log: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 28
```javascript
const obj = {
  prop: 1,
  func: function() {
    return this.prop;
  }
};
const func = obj.func;
console.log(obj.func());
console.log(func());
```

**Your Answer:**
```
obj.func(): _________________
func(): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 29
```javascript
console.log([] + {});
console.log({} + []);
```

**Your Answer:**
```
[] + {}: _________________
{} + []: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 30
```javascript
const arr = [1, 2, 3];
const result = arr.map(num => {
  if (num === 2) return;
  return num * 2;
});
console.log(result);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 31
```javascript
function foo(a) {
  arguments[0] = 10;
  console.log(a);
}
foo(5);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 32
```javascript
const obj = {
  x: 1,
  getX: () => {
    return this.x;
  }
};
console.log(obj.getX());
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 33
```javascript
console.log(true + false);
console.log(true + true);
console.log(true - false);
console.log(false - true);
```

**Your Answer:**
```
true + false: _________________
true + true: _________________
true - false: _________________
false - true: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 34
```javascript
const a = [1, 2, 3];
const b = [1, 2, 3];
const c = '1,2,3';
console.log(a == c);
console.log(b == c);
console.log(a == b);
```

**Your Answer:**
```
a == c: _________________
b == c: _________________
a == b: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 35
```javascript
function multiply(a, b) {
  return a * b;
}
console.log(multiply.length);
const partial = multiply.bind(null, 5);
console.log(partial.length);
```

**Your Answer:**
```
multiply.length: _________________
partial.length: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 36
```javascript
const obj = {
  counter: 0,
  increment: function() {
    setTimeout(function() {
      this.counter++;
      console.log(this.counter);
    }, 100);
  }
};
obj.increment();
```

**Your Answer:**
```
Output (after 100ms): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 37
```javascript
console.log(parseInt('10', 2));
console.log(parseInt('10', 8));
console.log(parseInt('10', 16));
```

**Your Answer:**
```
parseInt('10', 2): _________________
parseInt('10', 8): _________________
parseInt('10', 16): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 38
```javascript
const str = 'hello';
str[0] = 'H';
console.log(str);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 39
```javascript
console.log(Boolean('false'));
console.log(Boolean('0'));
console.log(Boolean([]));
console.log(Boolean({}));
```

**Your Answer:**
```
Boolean('false'): _________________
Boolean('0'): _________________
Boolean([]): _________________
Boolean({}): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 40
```javascript
const arr = [1, 2, 3];
const [a, , b] = arr;
console.log(a);
console.log(b);
```

**Your Answer:**
```
a: _________________
b: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 41
```javascript
function foo() {
  console.log(this.bar);
}
const obj1 = { bar: 'Hello' };
const obj2 = { bar: 'World' };
const boundFoo = foo.bind(obj1);
boundFoo.call(obj2);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 42
```javascript
const a = 10;
const b = new Number(10);
const c = 10;
console.log(a == b);
console.log(a === b);
console.log(b === c);
```

**Your Answer:**
```
a == b: _________________
a === b: _________________
b === c: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 43
```javascript
const obj = {
  a: 1,
  b: 2
};
Object.freeze(obj);
obj.a = 3;
obj.c = 4;
console.log(obj);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 44
```javascript
const arr = [1, 2, 3, 4, 5];
arr.forEach((item, index) => {
  if (item === 3) return;
  console.log(item);
});
```

**Your Answer:**
```
Output (in order): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 45
```javascript
function foo() {
  return
    {
      message: 'Hello'
    };
}
console.log(foo());
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 46
```javascript
const x = {};
const y = { key: 'y' };
const z = { key: 'z' };
x[y] = 'Hello';
x[z] = 'World';
console.log(x[y]);
console.log(x[z]);
```

**Your Answer:**
```
x[y]: _________________
x[z]: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 47
```javascript
console.log(Math.max());
console.log(Math.min());
```

**Your Answer:**
```
Math.max(): _________________
Math.min(): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 48
```javascript
const value = { number: 10 };
const multiply = (x = { ...value }) => {
  console.log(x.number *= 2);
};
multiply();
multiply();
multiply(value);
multiply(value);
```

**Your Answer:**
```
First multiply(): _________________
Second multiply(): _________________
Third multiply(value): _________________
Fourth multiply(value): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 49
```javascript
const arr = [1, 2, 3];
arr[6] = 7;
const result = arr.map(x => x * 2);
console.log(result);
```

**Your Answer:**
```
Output: _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

### Question 50
```javascript
const obj = {
  message: 'Hello',
  getMessage() {
    return this.message;
  }
};
const { getMessage } = obj;
console.log(getMessage());
console.log(obj.getMessage());
```

**Your Answer:**
```
getMessage(): _________________
obj.getMessage(): _________________
```

**Explanation (optional):**  
_____________________________________________________________________________

---

