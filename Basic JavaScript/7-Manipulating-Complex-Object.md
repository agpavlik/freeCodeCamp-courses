# Course - Basic JavaScript
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-javascript

---

## 87. Manipulating Complex Objects
Sometimes you may want to store data in a flexible Data Structure. A JavaScript object is one way to handle flexible data. They allow for arbitrary combinations of strings, numbers, booleans, arrays, functions, and objects.

Here's an example of a complex data structure:
```javascript
const ourMusic = [
  {
    "artist": "Daft Punk",
    "title": "Homework",
    "release_year": 1997,
    "formats": [ 
      "CD", 
      "Cassette", 
      "LP"
    ],
    "gold": true
  }
];
```
This is an array which contains one object inside. The object has various pieces of metadata about an album. It also has a nested formats array. If you want to add more album records, you can do this by adding records to the top level array. Objects hold data in a property, which has a key-value format. In the example above, "artist": "Daft Punk" is a property that has a key of artist and a value of Daft Punk.

### Note: 
You will need to place a comma after every object in the array, unless it is the last object in the array.

---

## 88. Accessing Nested Objects
The sub-properties of objects can be accessed by chaining together the dot or bracket notation.

Here is a nested object:
```javascript
const ourStorage = {
  "desk": {
    "drawer": "stapler"
  },
  "cabinet": {
    "top drawer": { 
      "folder1": "a file",
      "folder2": "secrets"
    },
    "bottom drawer": "soda"
  }
};

ourStorage.cabinet["top drawer"].folder2;
ourStorage.desk.drawer;
```
ourStorage.cabinet["top drawer"].folder2 would be the string secrets, and ourStorage.desk.drawer would be the string stapler.

>Exercise

Access the myStorage object and assign the contents of the glove box property to the gloveBoxContents variable. Use dot notation for all properties where possible, otherwise use bracket notation.
```javascript
const myStorage = {
  "car": {
    "inside": {
      "glove box": "maps",
      "passenger seat": "crumbs"
     },
    "outside": {
      "trunk": "jack"
    }
  }
};

const gloveBoxContents = undefined;
```
>Answer
```javascript
var myStorage = {
  "car": {
    "inside": {
      "glove box": "maps",
      "passenger seat": "crumbs"
     },
    "outside": {
      "trunk": "jack"
    }
  }
};

const gloveBoxContents = myStorage.car.inside["glove box"];
```
---

## 89. Accessing Nested Arrays
As we have seen in earlier examples, objects can contain both nested objects and nested arrays. Similar to accessing nested objects, array bracket notation can be chained to access nested arrays.

Here is an example of how to access a nested array:
```javascript
const ourPets = [
  {
    animalType: "cat",
    names: [
      "Meowzer",
      "Fluffy",
      "Kit-Cat"
    ]
  },
  {
    animalType: "dog",
    names: [
      "Spot",
      "Bowser",
      "Frankie"
    ]
  }
];

ourPets[0].names[1];
ourPets[1].names[0];
```
ourPets[0].names[1] would be the string Fluffy, and ourPets[1].names[0] would be the string Spot.

>Exercise

Using dot and bracket notation, set the variable secondTree to the second item in the trees list from the myPlants object.
```javascript
const myPlants = [
  {
    type: "flowers",
    list: [
      "rose",
      "tulip",
      "dandelion"
    ]
  },
  {
    type: "trees",
    list: [
      "fir",
      "pine",
      "birch"
    ]
  }
];
const secondTree = "";
```
>Answer
```javascript
const myPlants = [
  {
    type: "flowers",
    list: [
      "rose",
      "tulip",
      "dandelion"
    ]
  },
  {
    type: "trees",
    list: [
      "fir",
      "pine",
      "birch"
    ]
  }
];
const secondTree = myPlants[1].list[1];
```
---

## 90. Record Collection
>Exercise

You are creating a function that aids in the maintenance of a musical album collection. The collection is organized as an object that contains multiple albums which are also objects. Each album is represented in the collection with a unique id as the property name. Within each album object, there are various properties describing information about the album. Not all albums have complete information.

The updateRecords function takes 4 arguments represented by the following function parameters:

- records - an object containing several individual albums
- id - a number representing a specific album in the records object
- prop - a string representing the name of the album’s property to update
- value - a string containing the information used to update the album’s property

Complete the function using the rules below to modify the object passed to the function.
- Your function must always return the entire records object.
- If value is an empty string, delete the given prop property from the album.
- If prop isn't tracks and value isn't an empty string, assign the value to that album's prop.
- If prop is tracks and value isn't an empty string, you need to update the album's tracks array. First, if the album does not have a tracks property, assign it an empty array. Then add the value as the last item in the album's tracks array.
### Note:
A copy of the recordCollection object is used for the tests. You should not directly modify the recordCollection object.
```javascript
const recordCollection = {
  2548: {
    albumTitle: 'Slippery When Wet',
    artist: 'Bon Jovi',
    tracks: ['Let It Rock', 'You Give Love a Bad Name']
  },
  2468: {
    albumTitle: '1999',
    artist: 'Prince',
    tracks: ['1999', 'Little Red Corvette']
  },
  1245: {
    artist: 'Robert Palmer',
    tracks: []
  },
  5439: {
    albumTitle: 'ABBA Gold'
  }
};
// Only change code below this line
function updateRecords(records, id, prop, value) {
  return records;
}
updateRecords(recordCollection, 5439, 'artist', 'ABBA');
```
>Answer
```javascript
function updateRecords(id, prop, value) {
  if (value === '') {
    delete records[id][prop];
  } else if (prop !== "tracks") {
    records[id][prop] = value;
  } else {
    if (!records[id].hasOwnProperty('tracks')) {
      records[id].tracks = [];
      records[id].tracks.push(value);
    } else {
      records[id].tracks.push(value);
    }
  }
  return records;
}
```
