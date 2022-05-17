
You can think of an array as a list of things. For example a shopping list might look like 

```js
const shoppingList = ["apple", "arange", "pear"]
```


## Filter

This is a function to give you a new array back with only the items you want. For example, if you wanted to remove oranges from your shopping list.


```js
const shoppingList = ["apple", "orange", "pear"]
const filteredList = shoppingList.filter(item => item !== "orange")
// result is ["apple", "pear"]
```


## Map

This is a function to give you a new array back with the items you want transformed. For example, if you wanted to add "organic" infront of every item in your shopping list.

    
```js

const shoppingList = ["apple", "orange", "pear"]
const newList = shoppingList.map(item => "organic " + item)
// newList is ["organic apple", "organic orange", "organic pear"]
```

## Reduce

This is a difficult one to grasp. Basically, it takes an array and reduces it to a single value. For example, lets say we expanded the shopping list so it has a price for each item. Basically, when you call reduce you pass a function that takes the previous value and the current item and returns a new value. The value that comes after the function is the default or initial value.


```js
const shoppingList = [{ name: "apple", price: 1, quantity: 4}, { name: "banana", price: 2, quantity: 2}, { name: "orange", price: 3, quantity: 1}];
const totalPrice = shoppingList.reduce((total, item) => total + item.price * item.quantity, 0);
// totalPrice is 11
```

some people use reduce also as a way to combine a map and a filter in one function.

```js
const shoppingList = ["apple", "orange", "pear"]
// use reduce to filter out oranges and to add organic infront of each item
const reducedList = shoppingList.reduce((newList, item) => {
    if (item !== "orange") {
        newList.push("organic " + item) // only add the new item to the array if it is not an orange
    }
    return newList
}, [])
// reducedList is ["organic apple", "organic pear"]
```


## Some

Returns either true or false if any of the items match the item you are looking for. For example, if you wanted to know if any of the items in your shopping list are oranges.

    
```js
const shoppingList = ["apple", "orange", "pear"]
const hasOrange = shoppingList.some(item => item === "orange")
// hasOrange is true
```

if the array does not have an orange in it, the result will be false instead of true:


```js
const shoppingList = ["apple", "pear"]
const hasOrange = shoppingList.some(item => item === "orange")
// hasOrange is false
```


## Every

Returns either true or false if all of the items match the item you are looking for. For example, if you wanted to know if all of the items in your shopping list have organic in the name.

        
```js
const shoppingList = ["organic apple", "organic orange", "organic pear"]
const isEntirelyOrganic = shoppingList.every(item => item.includes("organic"))
// isEntirelyOrganic is true
```


## Find

Returns the first item that matches the item you are looking for. For example, if you wanted to get the first item in your shopping list that is an orange. If none are found it will return undefined.

            
```js   
const shoppingList = ["apple", "orange", "pear"]
const firstItem = shoppingList.find(item => item === "orange")
// firstItem is "orange"
```

or maybe the first item that you have more than one of (using the previous example)

    
```js  
const shoppingList = [{ name: "orange", price: 3, quantity: 1}, { name: "apple", price: 1, quantity: 4}, { name: "banana", price: 2, quantity: 2}];
const firstItemWithMoreThanOne = shoppingList.find(item => item.quantity > 1)
// firstItemWithMoreThanOne is { name: "apple", price: 1, quantity: 4}
```

