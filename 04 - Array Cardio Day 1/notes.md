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
```
const totalYears = inventors.reduce((total, inventor) => {
  return total + (inventor.passed - inventor.year);
}, 0 );
```
Needs to put the zero in at the end otherwise we get a long number where total is underfined at the beginning.

#### Question five :

Already refactored

#### Question six :

* Load link in new browser window
* Select the correct section
      const category = document.querySelector('.mw-category');
* Select all links in that section
      const links = category.querySelectorAll('a');
* Maps over the list of links and returns the list text textContent
      const de = links.map(link => link.textContent);
* Code is currently :
      const category = document.querySelector('.mw-category');
      const links = category.querySelectorAll('a');

      const de = links.map(link => link.textContent);
  But querySelector returns a nodelist which we cannot run map on, so the links list will need to be turned into an array. You can do this by :
      const links = Array.from(category.querySelectorAll('a'));

          OR use spread method

      const links = [...category.querySelectorAll('a')];
