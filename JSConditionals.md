`Concept 1` &nbsp;**Data Types**

There are 8 data types in JS.

- `Objects (as data type)` - data as properties, often written in key:value pairs `{firstName:'Kat'}`
- `String` - series of characters
- `Number` - integers (whole numbers) and floating-point numbers (numbers w/ decimals)
- `Boolean` - true or false
- `Null` - intentional absence of a value, set to null
- `Undefined` - a variable that has not been assigned a value or is set to undefined (ex. let)
- `Symbol` - a unique property key, created with `Symbol()`
- `BigInt` - numbers that are greater than the Number type can handle, created by adding an `n` to a number Ex. `10n`. Due to the way Javascript encodes and stores numbers, JS can only be precise when processing numbers between -(2<sup>53</sup> – 1) and 2<sup>53</sup> – 1. Because of this, JS will start to round extremely large numbers and be unable to correctly evaluate the value. For reference: 2<sup>53</sup> – 1 is 9,007,199,254,740,991.
  **Incorrect evaluation (which can lead in incorrect authentication, etc.)**
  ```Javascript
  9,007,199,254,740,991 + 1 === 9,007,199,254,740,991 + 2
  // JS will evaluate this as true, even though it's mathematically incorrect
  ```
  **Rounding values, changing our data. This can be prevented by using the BigInt data type**
  ```Javascript
  console.log(9007199254740995) // > 9007199254740996 (incorrect)
  console.log(9007199254741985) // > 9007199254741984 (incorrect)
  console.log(9007199254740998n) // > 9007199254740998n (correct)
  ```

<hr>

`Concept 2` &nbsp;**Truthy vs. Falsy & Type Conversion**

Sometimes we need to evaluate a value as true/false regardless of it's data type. 'Falsy' values are those which evaluate to false. 'Truthy' values are those which evaluate to true.

- `Falsy` =
  - `null` - `null`
  - `undefined` -`undefined`
  - `false` - `boolean`
  - `NaN` - `number`
  - `0` - `number`
  - `-0` - `number`
  - `0n` - `bigInt`
  - `""` - `string`
- `Truthy` = any value which is not falsy

```Javascript
if ('') {
  console.log('true')
} else {
  console.log('false')
}
```

**Type Coercion (Implicit Type Conversion)** is the automatic conversion of value from one data type to another. (A value can only be converted to a string, number, or boolean)

<hr>

`Concept 3` &nbsp;**Conditionals** <br> If/Else Statment

```Javascript
if(thisIsTrue) {
    doThis
} else {
    doThisInstead
}
```

<br>
Ternary Operator

```Javascript
{ifThisIsTrue ? doThis : elseDoThis}
```

<br>
Logical AND Operator

```Javascript
{ifThisIsTrue && doThis}
```

```Javascript
{ifThisIsFalse && ignoreThis}
// > returns the value of ifThisIsFalse
```

```Javascript
console.log(false && "hello world");
// > false
```

<br>
Logical NOT Operator (Inverts a true or false value)

```Javascript
value = true
!value = false
```

```Javascript
value = false
!value = true
```

<hr>

`Concept 4` &nbsp;**Ternary vs Logical AND**

It's important to consider the desired outcome & be explicit with logic. Similar expressions can return different values.

```Javascript
let count = 0;

  return (
    <div>
      <p>Count: {count ? { count } : null}</p>
      // > Count:
      <p>Count: {count && { count }}</p>
      {console.log(typeof count)}
      // > Count: 0
    </div>
  );
```

<hr>
