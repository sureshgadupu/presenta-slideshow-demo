---
colors: ""
fonts: five
transition: fadeIn
---

# ES 2021 New Features

---

<!--

notes: This is a presenter note 2!
-->

## <code>String.replaceAll method</code>

<span style="font-size:15px;">
- The replaceAll method returns a new string in which all occurrences of a pattern are replaced by a replacement passed to it <br/>
- The pattern parameter can either be a string or a regex pattern <br/>
- The replaceAll method is a sequel to the String.replace method, which only replaces the first occurrence of the pattern with replacement
<br/>
<br/>
<mark>
<code> const newString = oldString.replaceAll(pattern, replacement); </code>

</mark>
</span>

---

Example

<span style="font-size:15px;">

<mark>

<code>

const str = "Linda is a self-taught developer.Linda will rule the world";

</code>
</mark>

Before ES 2021

<mark>
<code>

let newStr = str.replace( new RegExp("Linda", "g"), "Micheal");
console.log(newStr);

//output: Micheal is a self-taught developer.Micheal will rule the world

</code>
</mark>
<br/>
<br/>
<mark>
<code>

let newStr = str.replace(/Linda/g, "Micheal");
console.log(newStr);

//output: Micheal is a self-taught developer.Micheal will rule the world
</code>
</mark>

</span>

---

<span style="font-size:15px;">

ES 2021

<span style="font-size:15px;">
<mark>
<code>
let newStr = str.replaceAll("Linda","Micheal");

console.log(newStr);

//output: Micheal is a self-taught developer.Micheal will rule the world

</code>
</mark>
 </span>

---

<!--
steps: li
notes: This is a presenter note 2!
-->

## <code> Numeric separator </code>

<span style="font-size:15px;">
The numeric separator simply improves the readability of large numbers by using the underscore (_) character to separate number groups, just like you use commas to separate numbers in writing

<mark><code> const largenumber = 1_200_044_555; <code> <br/> output :1200044555</mark>
<br/>

<mark><code> const largenumber = 12_00_044_555; <code> <br/> output : 1200044555</mark>

<mark><code> const decimalnumber = 12.4_556; <code> <br/> output : 12.4556</mark>

<mark><code> const decimalnumber = 12.455_6; <code> <br/> output : 12.4556</mark>

</span>

---

<span style="font-size:15px;">
It can be used for binary and Hex literals: <br/>
<mark>
<code>
const max8bits = 0b1111_1111; <br/>
const message = 0xA0_B0_C0;
</code>
</mark>
</span>
---

## <code> Promise.any method </code>

<span style="font-size:15px;">
The Promise.any() method takes arraof promises returns a promise that will resolve as soon as one of the promises are resolved. If all of the promises are rejected, the method will throw an AggregateError exception holding the rejection reasons.
</span>

---

<span style="font-size:15px;">

<p> example: </p>

 <mark>
 <code>
    const promiseOne = new Promise((resolve, reject) => { <br/>
    setTimeout(() => resolve("one"), 3000); <br/>
    });
    <br/> <br/>
const promiseTwo = new Promise((resolve, reject) => { <br/>
  setTimeout(() => resolve("two"), 2000);<br/>
});<br/> <br/>
const promiseThree = new Promise((resolve, reject) => {<br/>
  setTimeout(() => resolve("three"), 1000); <br/>
}); <br/> <br/>
Promise.any([promiseOne, promiseTwo, promiseThree]).then( <br/>
  (first) => { <br/>
    // Any of the promises was fulfilled.
    console.log(first); // three <br/>
  },<br/>
  (error) => { <br/>
    // handling error here
  }<br/>
);
</code>
</mark>
</span>

---

<span style="font-size:15px;">
Example using the async/await syntax:

<mark>
<code>
 const promiseOne = new Promise((resolve, reject) => { <br/>
    setTimeout(() => reject("one"), 3000); <br/>
    });
    <br/> <br/>
const promiseTwo = new Promise((resolve, reject) => { <br/>
  setTimeout(() => reject("two"), 2000);<br/>
});<br/> <br/>
const promiseThree = new Promise((resolve, reject) => {<br/>
  setTimeout(() => reject("three"), 1000); <br/>
}); <br/> <br/>
try { <br/>
  const first = await Promise.any([promiseOne, promiseTwo,promiseThree ]); <br/>
  // Any of the promises was fulfilled. <br/>
} catch (error) { <br/>
  console.log(error); <br/>
  // AggregateError: All promises were rejected
}
</code>
</span>
---
## <code> Logical assignment operator </code>

<span style="font-size:15px;">
The logical assignment operator combines Logical Operators and Assignment Expressions, allowing you to write a shorter syntax for variable value checking.
<br/>
<mark>
<code>
 let x; <br/>
if(!x){ // if x is undefined , assign number 7<br/>
  x = 7; <br/>
}
</code>
</mark>

above code can be written as
<mark>
<code>
let x;
x ||= 7; // since x is undefined, it's assigned the number 7
console.log(x);
</code>
</mark>
</span>

---

<span style="font-size:15px;">
The logical assignment works with logical AND (&&) and nullish coalescing operator (??) as well:

<mark>
<code>

let x = null;
x ??= 7 // assign 7 to x when it's null or undefined

let y = "Hello";
y &&= 9 // assign 9 to y when it's value is truthy

</code>
</mark>
</span>
---
 Features not covered in this presentation
 - WeakRefs
 - Finalizers

---

# This presentation is made with PRESENTA Lib

---

# Thank you! :heart:
