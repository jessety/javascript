JavaScript Style Guide
==========

JavaScript is a very loose language, which therefore requires more strict guidelines. Everyone needs a set of standards.

## Indentation

Never mix spaces and tabs. Also, never use tabs. Instead, use 2 or 4 spaces to indent code- and stick with it.

## Semicolons

Always use semicolons to end lines. This leads to more readable code, and less unintentional mistakes.

## Properties

Use dot notation to access properties

```js
if (request.url === x)
```

Instead of

```js
if (request['url'] === x)
```

## Comparison

Always use === or ==!, instead of == or =!. Fuzzy comparisons lead to bad code.

```js
if (number === 0.1) {
    
}
```

Instead of 

```js
if (maybeNumber == 0.1) {
    
}
```

## Single Quotes

Use single quotes instead of double quotes. Always.

```js
var message = 'Test successful';
```

Instead of 

```js
var message = "Test successful";
```

## Object Creation

Always use literal syntax for object / array creation. 

```js
var object = {},
    array = [];
```

Instead of

```js
var object = new Object(),
    array = new Array();
```

Omit the quotes in property names when creating an object

```js
var guitar = {
	type: 'martin'
};
```

Instead of 

```js
var guitar = {
	'type': 'martin'
};
```

## Braces

Always use braces, even in 1-line statements where they’re not necessary.

```js
if (condition) {
	react();
}
```

Instead of

```js
 if (test) react();
 ```
 
Put the curly brace at the end of a function declaration, if statement, or loop on the same line as the declaration itself. This goes for else statements as well.

```js
if (somethingIsTrue) {
    react();
} else {
    doNotReact();
}
```

Instead of 

```js
if (somethingIsTrue)
{
    react();
}
else
{
    doNotReact();
}
```
 
Put exactly one space between the the parenthesis at the end of a function declaration, if statement, or loop and it’s respective brace.

```js
if (somethingIsTrue) {
    react();
}
```

Instead of 

```js
if (somethingIsTrue)          {
    react();
} 
```
## Spacing

Put exactly one space between the statement and parenthesis in conditional statements or loops, but not functions.

```js
function potentialProblem(problem, issue) {
    if (problem || issue) {
        for (var potentialSolution in potentialSolutions) {
        
        }
    }
}
```

Instead of

```js
function potentialProblem (problem, issue) {
    if(problem || issue) {
        for(var potentialSolution in potentialSolutions) {
        
        }
    }
}
``` 

Always put exactly on space between function parameters

```js
test.call(param, param2, param3);
```

Instead of

```js
test.call(param,param2,param3);
```

Always put spaces between quote parameters

```js
console.log('The error message is: ' + message + '!')
```

Instead of

```js
console.log('The error message is: '+message+'!')
```

## Variables

Never initialize variables to 'undefined'. Initializing them without a value is the same thing, and cleaner.

```js
var i;
```

Instead of

```js
var i = undefined;
```

## Functions

Never return undefined. Returning without a value, or not at all, is the same thing.

```js
function test(temperature) {
    if (temperature > 45) {
        return 'Too Hot!';
    }
}
```

Instead of

```js
function test(temperature) {
    if (temperature > 45) {
        return 'Too Hot!';
    } else {
        return undefined;
    }
}
```

Always test for failure conditions first. Don't nest positive conditions in braces. This leads to cleaner, more readable code.

```js
function addResult(temperature) {
    if (temperature < 0) {
        //We don't care about samples below freezing
        return false;
    }
    
    var date = new Date();
    
    if (date.getDay() !== 0) {
        //We only care about samples taken on Mondays
        return false;
    }
    
    results.push(temperature); 
    
    return true;
}
```

Instead of

```js
function addResult(temperature) {
    
    //We don't care about samples below freezing
    if (temperature > 0) {
        
        var date = new Date()
        
        //We only care about samples taken on Mondays
        if (date.getDay() === 0) {
        
            results.push(temperature);
            return true;
            
        } else {
            return false;
        }
    } else {
        return false;
    }
}
```
