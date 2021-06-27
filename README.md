# Question 1
Please create a web application following below specs.
-	Angular framework is preferred, but you can also use your preferred framework, or pure javascript/HTML5
-	Page consist of 3 columns, first column has fixed width of 200px, last column has fixed width of 300px, the middle column expand/shrink to fill the remaining space of the page, and should be at least 100px. If window is smaller than 600px, show the scrollbar.
-	In the first column, create an input field, where user can enter any number. If the value entered by users are not integer, round it to the nearest integer. If user enter negative values, replace it with 1.
-	In the second column, show a drop down, which user can choose what calculation between “isPrime” and “isFibonacci”  he wants to calculate, default the value to isPrime. 
o	isPrime: calculate whether the input is a prime number, show true in Col3 if the number is prime, and false in the other case
o	IsFibanacci: calculate whether the input is a fibonacci number, show true in Col3 if the number is a fibonacci number, and false in the other case.
-	Whenever the value in input box in column1, or the dropdown in column2 changes, execute the calculation accordingly, and show the result in column 3.


# refinitiv-s2q1

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
