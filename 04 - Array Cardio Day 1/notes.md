* console.table => logs a table with the results in the console.

#### Question one :
```
const fifteen = inventors.filter(function(inventor){
  if(inventor.year >= 1500 && inventor.year < 1600) {
    return true;
  }
});
```
Once refactored:
```
const fifteen = inventors.filter(inventor => (inventor.year >= 1500 && inventor.year < 1600))
```

#### Question two :
```
const fullNames = inventors.map(inventor => inventor.first + ' ' + inventor.last)
```
Can also be written like:
```
const fullNames = inventors.map(inventor => `${inventor.first} ${inventor.last}`)
```

#### Question three :
```
const order = inventors.sort(function(a,b){
  if (a.year > b.year) {
    return 1
  } else {
    return -1
  }
});
```
Once refactored:
```
const order = inventors.sort((a,b) => a.year > b.year ? 1 : -1);
```

#### Question four :
