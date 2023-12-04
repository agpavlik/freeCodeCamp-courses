# Caesars Cipher

> Exercise

One of the simplest and most widely known ciphers is a Caesar cipher, also known as a shift cipher. In a shift cipher the meanings of the letters are shifted by some set amount. A common modern use is the `ROT13 cipher`, where the values of the letters are shifted by 13 places. Thus `A ↔ N`, `B ↔ O` and so on. Write a function which takes a ROT13 encoded string as input and returns a decoded string.All letters will be uppercase. Do not transform any non-alphabetic character (i.e. spaces, punctuation), but do pass them on.

> Answer variant 1

```javascript
let abc = {
  A: "N",
  B: "O",
  C: "P",
  D: "Q",
  E: "R",
  F: "S",
  G: "T",
  H: "U",
  I: "V",
  J: "W",
  K: "X",
  L: "Y",
  M: "Z",
  N: "A",
  O: "B",
  P: "C",
  Q: "D",
  R: "E",
  S: "F",
  T: "G",
  U: "H",
  V: "I",
  W: "J",
  X: "K",
  Y: "L",
  Z: "M",
};

function rot13(str) {
  let code = str.split("");
  let decoded = [];

  decoded = code.map(function (message) {
    console.log(message);
    if (abc.hasOwnProperty(message)) {
      message = abc[message];
    }
    return message;
  });
  return decoded.join("");
}
```

> Answer variant 2

```javascript
function rot13(str) {
  const Acode = "A".charCodeAt();
  const Ncode = "N".charCodeAt();
  const Zcode = "Z".charCodeAt();
  return [...str]
    .map(function (e) {
      const code = e.charCodeAt();
      if (Acode <= code && code <= Zcode) {
        if (code < Ncode) {
          return String.fromCharCode(code + 13);
        } else {
          return String.fromCharCode(code - 13);
        }
      } else {
        return e;
      }
    })
    .join("");
}
```

> Answer variant 3

```javascript
function rot13(str) {
  return str.replace(/[A-Z]/g, (L) =>
    String.fromCharCode((L.charCodeAt(0) % 26) + 65)
  );
}
```

> Answer variant 4

```javascript
function rot13(str) {
  let regex = /./g;
  let newStr = str.match(regex).join("");
  let newArr = [];
  for (let i = 0; i < newStr.length; i++) {
    let number = newStr.charCodeAt(i);
    if (number < 78 && number >= 65) {
      number += 13;
    } else if (number <= 90 && number >= 78) {
      number -= 13;
    }
    newArr.push(String.fromCharCode(number));
  }
  newArr = newArr.join("");
  return str.replace(newStr, newArr);
}
```

> Answer variant 5

```javascript
function rot13(str) {
  const alphabet = [
    "A",
    "B",
    "C",
    "D",
    "E",
    "F",
    "G",
    "H",
    "I",
    "J",
    "K",
    "L",
    "M",
    "N",
    "O",
    "P",
    "Q",
    "R",
    "S",
    "T",
    "U",
    "V",
    "W",
    "X",
    "Y",
    "Z",
  ];
  return str
    .split("")
    .map((el) => {
      let indexOfEl = alphabet.indexOf(el);
      return alphabet.indexOf(el) === -1
        ? el
        : indexOfEl - 13 < 0
        ? alphabet[indexOfEl + 13]
        : alphabet[indexOfEl - 13];
    })
    .join("");
}
```

> Answer variant 6

```javascript
function rot13(str) {
  const alphabet = [
    "A",
    "B",
    "C",
    "D",
    "E",
    "F",
    "G",
    "H",
    "I",
    "J",
    "K",
    "L",
    "M",
    "N",
    "O",
    "P",
    "Q",
    "R",
    "S",
    "T",
    "U",
    "V",
    "W",
    "X",
    "Y",
    "Z",
  ];

  const decodedStr = [...str].reduce((acc, el) => {
    if (el.match(/[A-Z]/)) {
      let index = alphabet.indexOf(el);
      acc += alphabet[index >= 13 ? index - 13 : index + 13];
    } else {
      acc += el;
    }
    return acc;
  }, "");

  return decodedStr;
}
```
