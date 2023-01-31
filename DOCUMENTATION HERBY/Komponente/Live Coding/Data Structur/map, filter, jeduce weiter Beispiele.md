Here's a sample piece of Star Wars data from the [Star Wars API](https://swapi.dev/).

```javascript
const characters = [
    {
        name: 'Luke Skywalker',
        height: '172',
        mass: '77',
        eye_color: 'blue',
        gender: 'male',
    },
    {
        name: 'Darth Vader',
        height: '202',
        mass: '136',
        eye_color: 'yellow',
        gender: 'male',
    },
    {
        name: 'Leia Organa',
        height: '150',
        mass: '49',
        eye_color: 'brown',
        gender: 'female',
    },
    {
        name: 'Anakin Skywalker',
        height: '188',
        mass: '84',
        eye_color: 'blue',
        gender: 'male',
    },
];
```

## [Map](https://youtu.be/G6J2kl1aVao)

1. Get an array of all names
2. Get an array of all heights
3. Get an array of objects with just name and height properties
4. Get an array of all first names

## [REDUCE](https://youtu.be/0aJ65a6LsSc)

1. Get the total mass of all characters
2. Get the total height of all characters
3. Get the total number of characters in all the character names
4. Get the total number of characters by eye color (hint. a map of eye color to count)

## [FILTER](https://youtu.be/3LOEGS4qcRM)

1. Get characters with mass greater than 100
2. Get characters with height less than 200
3. Get all male characters
4. Get all female characters

---

```js
const characters = [
    {
        name: 'Luke Skywalker',
        height: 172,
        mass: 77,
        eye_color: 'blue',
        gender: 'male',
    },
    {
        name: 'Darth Vader',
        height: 202,
        mass: 136,
        eye_color: 'yellow',
        gender: 'male',
    },
    {
        name: 'Leia Organa',
        height: 150,
        mass: 49,
        eye_color: 'brown',
        gender: 'female',
    },
    {
        name: 'Anakin Skywalker',
        height: 188,
        mass: 84,
        eye_color: 'blue',
        gender: 'male',
    },
];

//***MAP***
//1. Get array of all names
//2. Get array of all heights
//3. Get array of objects with just name and height properties
//4. Get array of all first names

//***REDUCE***
//1. Get total mass of all characters
//2. Get total height of all characters
//3. Get total number of characters by eye color
//4. Get total number of characters in all the character names

//***FILTER***
//1. Get characters with mass greater than 100
//2. Get characters with height less than 200
//3. Get all male characters
//4. Get all female characters

```