
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
---
> Answer variant 2
```javascript
function convertToRoman(num) {
  if(num < 1){ return "";}
  if(num >= 1000){ return "M" + convertToRoman(num - 1000);}
  if(num >= 900){ return "CM" + convertToRoman(num - 900);}
  if(num >= 500){ return "D" + convertToRoman(num - 500);}
  if(num >= 400){ return "CD" + convertToRoman(num - 400);}
  if(num >= 100){ return "C" + convertToRoman(num - 100);}
  if(num >= 90){ return "XC" + convertToRoman(num - 90);}
  if(num >= 50){ return "L" + convertToRoman(num - 50);}
  if(num >= 40){ return "XL" + convertToRoman(num - 40);}
  if(num >= 10){ return "X" + convertToRoman(num - 10);}
  if(num >= 9){ return "IX" + convertToRoman(num - 9);}
  if(num >= 5){ return "V" + convertToRoman(num - 5);}
  if(num >= 4){ return "IV" + convertToRoman(num - 4);}
  if(num >= 1){ return "I" + convertToRoman(num - 1);}  
}

convertToRoman(36);
```
---
> Answer variant 3
```javascript
function convertToRoman(num) {
  let singles = ["", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"];
  let tens = ["", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"];
  let hundreds = ["", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"];
  let thousands = ["", "M", "MM", "MMM", "MMMM"];
  let length = num.toString().length;
  let numbers = num.toString().split("").map(Number);
  let romanNum = '';

  let i = 0;
  
  switch (length) {
    case 4:
      romanNum = thousands[numbers[i]];
      i++;
    case 3:
      romanNum += hundreds[numbers[i]];
      i++;
    case 2:
      romanNum += tens[numbers[i]];
      i++;
    case 1 :
      romanNum += singles[numbers[i]];
  }
 return romanNum;
}

convertToRoman(36);
```
---

> Answer variant 4
```javascript
function convertToRoman(num) {
  const romanLookUp = {M:1000, CM:900,D:500,CD:400,C:100,XC:90,L:50,XL:40,X:10,IX:9,V:5,IV:4,I:1}
  let result = ''

  Object.keys(romanLookUp).sort((a,b)=>romanLookUp[b]-romanLookUp[a]).forEach((key)=>{
    while(num>=romanLookUp[key]){
      result+=key;
      num-=romanLookUp[key]
    }
  })
  return result;
}

convertToRoman(36);
```
---

> Answer variant 5
```javascript
function convertToRoman(num) {
  const input = {
    1: 'I',
    2: 'II',
    3: 'III',
    4: 'IV',
    5: 'V',
    6: 'VI',
    7: 'VII',
    8: 'VIII',
    9: 'IX',
    10: 'X',
    20: 'XX',
    30: 'XXX',
    40: 'XL',
    50: 'L',
    60: 'LX',
    70: 'LXX',
    80: 'LXXX',
    90: 'XC',
    100: 'C',
    200: 'CC',
    300: 'CCC',
    400: 'CD',
    500: 'D',
    600: 'DC',
    700: 'DCC',
    800: 'DCCC',
    900: 'CM',
    1000: 'M'
  }

  let arrNum = [];

  if (num <= 10) {
    arrNum.push(num);

  } else if (num > 11 && num <= 99) {
    arrNum.push(
      ((Math.floor(num/10))*10), 
      (num - ((Math.floor(num/10))*10)));

  } else if (num >= 100 && num <= 999) {
    arrNum.push(
      ((Math.floor(num/100))*100), 
      ((Math.floor((num - ((Math.floor(num/100))*100))/10))*10), 
      (num - ((Math.floor(num/100))*100) - ((Math.floor((num - ((Math.floor(num/100))*100))/10))*10)));

  } else if (num >= 1000) {
    arrNum.push(
      ((Math.floor(num/1000))*1000), 
      ((Math.floor((num - ((Math.floor(num/1000))*1000))/100))*100),
      ((Math.floor((num - ((Math.floor(num/1000))*1000) - ((Math.floor((num - ((Math.floor(num/1000))*1000))/100))*100))/10))*10), 
      (num - ((Math.floor(num/100))*100) - ((Math.floor((num - ((Math.floor(num/100))*100))/10))*10) - ((Math.floor((num - ((Math.floor(num/1000))*1000) - ((Math.floor((num - ((Math.floor(num/1000))*1000))/100))*100))/10))*10)));

  } else {
    return 0;
  }

  let arabicNum = [];
  let arrNumStr = arrNum.join().split(',');
  console.log(arrNum);
  console.log(arrNumStr);
  for (let key in input) {
    if (arrNumStr.includes(key)) {
      arabicNum.push(input[key]);
    }
  }
  console.log(arabicNum)
  console.log(arabicNum.reverse().join("").toString());
  return arabicNum.reverse().join("").toString();
}

convertToRoman(12);
```