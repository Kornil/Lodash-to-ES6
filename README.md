# Lodash-to-ES6
How to convert some common lodash methods to ES6, will update as I find other lodash stuff on the code I'm working on. Feel free to correct or shorten my golf game.

### noop
noop is a simple function that always returns `undefined`

```
// lodash & lodash/fp
_.noop; // => 'undefined'

// ES6
() => undefined;

// Codegolf
x;f=>x
```

### lodash constant & lodash/fp always
constant & always return what you specify

```
// lodash
_.constant(x); // returns x

// lodash/fp
_.always(x); // returns x

// ES6
() => x;

// Codegolf
f=>!!1 // true
f=>!!0 // false
f=>x // whatever you want
```

### identity
return the given value

```
// lodash & lodash/fp
_.identity(x); // returns x

// ES6
(x) => x;

// Codegolf
x=>x
```

### isUndefined
check if the value is undefined

```
// lodash & lodash/fp
_.isUndefined(x); // true or false

// ES6
typeof x === 'undefined';
// or
x === void 0;

// Codegolf
f;x==f
```

### isArray
check if value is an array

```
// lodash & lodash/fp
_.isArray(x); // true or false

// ES6
Array.isArray(x);

// Codegolf
// .push is unique to arrays so if you don't have objects with a 'push' key, this is safe
x.push&&!!1 // true or undefined
x.push?!!1:!!0 // true or false
```

### isString
check if value is a string

```
// lodash & lodash/fp
_.isString(x); // true or false

// ES6
typeof x === 'string';
// for checking 'new String()' add the following
x instanceof String;

// Codegolf
x===x+''
```

### isObject
check if value is Object (arrays, functions, objects, regexes, stuff with `new`)

```
// lodash & lodash/fp
_.isObject(x); // true or false

// ES6
x === Object(x);

// Codegolf
x===Object(x) // no idea how to optimize this
```

### isEmpty
check if value is empty (arrays, objects, strings)

```
// lodash & lodash/fp
_.isEmpty(x); // true or false

// ES6
x.length === 0;

// Codegolf
!x.length
```

### toLower
convert string to lowercase

```
// lodash & lodash/fp
_.toLower(x);

// ES6
x.toLowerCase();

// Codegolf
// if you are not allowed to use .toLowerCase()
x.replace(/[A-Z]/g,$=>String.fromCharCode($.charCodeAt()+32)))
```
