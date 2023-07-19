
# Roman Numeral Converter

> Exercise

Convert the given number into a roman numeral.

| Roman numerals | Arabic numerals |
| :- | :- |
| M	| 1000 |
| CM | 900 |
| D	| 500 |
| CD |	400 |
| C	| 100 |
| XC |	90 |
| L	| 50 |
| XL | 40 |
| X	| 10 |
| IX | 9 |
| V	| 5 |
| IV | 4 |
| I	| 1 |
All roman numerals answers should be provided in upper-case.

> Answer variant 1
```javascript
function convertToRoman(num) {
  const input = {M:1000,CM:900,D:500,CD:400,C:100,XC:90,L:50,XL:40,X:10,IX:9,V:5,IV:4,I:1};
  let romanNum = '';
  for (let i in input) {
    while ( num >= input[i] ) {
      romanNum += i;
      num -= input[i];
    }
  }
  return romanNum;
}

convertToRoman(36);
```
