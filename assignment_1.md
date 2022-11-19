Problem 1: In 3-4 sentences, please explain what Big O Notation is.
Big O notation represents the difficulty of a computational task dependent on the amount of data set given. The time and space complexity of a computation are determined differently through 5 different measurements from simple to complex. Big O notation is used to determine the best solution to the problem given. 


Problem 2: For each of the time complexities shown below: 
a - Name the complexity
b - Rank from 1-5 (1 being the best, 5 being the worst) 
c - Describe in 1-2 sentences of the complexity
d - Provide a code example of how the complexity works

    O(n!)

a - Factorial Time Complexity
b- Rank - 5 
c - The more data given to this, the more operations are needed to perform. 6! = 6 X 5 X 4 X 3 X 2 X 1
d - const factorial = n => {
    let num = n;

    if (n === 0) return 1
    for (let i = 0; i < n; i++) {
        num = n * factorial(n - 1);
    };

    return num;
};
    O(N^2)

a - Quadratic Time Complexity
b - Rank - 4
c - This is when you increase the size of the input by a multiplication factor
d - for (let i = 0; i < arr1.length; i++) {
    for (let i = 0; i < arr1.length; i++) {
        console.log(arr1[i]); 
    }    
}

    O(1)
a - Contant Time Complexity
b - Rank - 1
c - However big the data size input is, the amount of time to complete the operation is the same. This creates the best ideal scenario for computation.
d - const twoSum = (num1, num2) => {
    return num1 + num2; 
}

    O(N)
a - Linear Time Complexity
b - Rank - 3
c - This is a one to one proportional relationship between items and operations. 
d - while (arr.length < 10) {
    console.log(arr)
}

    O(log n)
a - Logarithmic Time Complexity
b - Rank - 2
c - A complexity in which the time to execute is proportional to the logarithm of the input size. This complexity doesn't looks at every element of an input. 
d - const logTime = (arr) => {
	let numberOfLoops = 0; 
  
  for(let i = 1; i < arr.length; i *=2) {
		numberOfLogs++
	}
  
  return numberOfLoops
}

let loopsA = logTime([1])
let loopsB = logTime([1, 2]) 
let loopsC = logTime([1, 2, 3, 4]) 

Problem 3: Name 3 reasons why we care about Big O and we care about code performance.

1 - We need to find the fastest way to solve a problem. Time is money.
2 - As data set increases, we need a way to better handle the amount of data. 
3 - Code competency is key in interviews.

Problem 4: What is the problem of using a time method such as performance.now() to measure how “fast” a 
code runs on our machines. 
Every system is different and will process different times and is not the most accurate way of measuring code performance. 

Problem 5: Given the following piece of code: 
- Explain what the TOTAL time complexity is 
o For example, if a function had one linear and a nested for…loop, it would be: n + n^2
- Explain what the CONSOLIDATED time complexity is
o For example, if a function had one linear and a nested for…loop, it would condense to: n^2
const someFunction = (arr1) => {
 arr1.push(1).pop()                         // O(1)
 
 for (let i = 0; i < arr1.length; i++) {    // O(N)
 console.log('do something 2')               // O(1)
 }
 
 for (let i = 0; i < arr1.length; i++) {    // O(N)
 console.log('do something 3')              // O(1)
 }
 
 for (let i = 0; i < arr1.length; i++) { // O(N)        // O(N^2)
 for (let i = 0; i < arr1.length; i++) { // O(N)
 console.log('do something 3')           // O(1)
 }
 }
}

Consolidated time complexity = 4 + 2n + n^2 = O(N^2)


Problem 6: Given the following piece of code: 
- Explain what the TOTAL time complexity is 
o For example, if a function had one linear and a nested for…loop, it would be: n + n^2
- Explain what the CONSOLIDATED time complexity is
o For example, if a function had one linear and a nested for…loop, it would condense to: n^2
const someFunction1 = (arr1) => {
 let sum = arr1[1] + arr[2]                   // O(1)
 
 while (condition) {                          // O(N)
 sum = arr[5] + arr[7]                        // O(1)
 }
 
 for (let i = 0; i < arr1.length; i++) {    // O(N)
 for (let i = 0; i < arr1.length; i++) {    // O(N)
 for (let i = 0; i < arr1.length; i++) {    // O(N)
 console.log('do something 3')
 }
 }
 }
}

Consolidated time complexity = 1 + n + 1 + n^3 = O(n^3)

Problem 7: Please explain in 3-5 sentences why we can ignore constants and consolidate our time complexities.
We ignore constants because as the computations get more complex the only thing that matters is the amount of time spent solving a problem. The computational time complexity will have more impact on the performance of the code rather than the constants. So the more operations that are needed the more time complexity there is. 


Problem 8: In 2-3 sentences, please explain what space complexity is and why we care. 
Space complexity is the amount of input data space taken by the algorithm. We care because it takes memory and affects the performance of the code. 


Problem 9: Given the following data TYPES, label what the space complexity is for each one: 
- Boolean       -Constant
- Undefined     -Constant
- Null          -Constant
- Numbers       -Constant
- String        -Linear
- Array         -Linear
- Object        -Linear


Problem 10: Give two reasons when you should use a array and when you should use a object. 
You should only use an array if you need fast access to the elements and you need to order the elements. You should only use an object if you don't need ordering and if you don't need fast access to any of the elements. 


Problem 11: Given the following object methods, label what the TIME complexity is for each one: 

const obj = {
 name: 'tony'
}
//inserting
obj.age = 44;                   // Constant Time

//removing                      // Constant Time
delete obj.age;

//searching 1                   // Linear Time
obj.hasOwnProperty['name']

//searching 2                   // Linear Time
for (const prop in obj) {
 console.log(obj[prop])
}

//accessing                     // Constant Time
obj.age //44

//retrieving keys               // Constant Time
Object.keys(obj)

//retrieving values             // Constant Time
Object.values(obj)


Problem 12: Given the following array methods, label what the TIME complexity is for each one:
const arr2 = [1, 2, 3, 4, 5, 6, 7];

//inserting 1                   //  Linear/Constant Time
arr2.push(8)
//inserting 2                   //  Linear/Constant Time
arr2.unshift(0)
//removing 1                    //  Linear/Constant Time
arr2.pop()
//removing 2                    //  Linear/Constant Time
arr2.shift()
//searching 1                   //  Linear Time
const findNumber = arr2.find(num => num === 2)
//searching 2                   //  Linear  Time
for (let i = 0; i < arr2.length; i++) {
 if (arr2[i] === 2) {
 return arr2[i]
 }
}
//retrieving                    // Constant Time           
const getNumber = arr2[3]
//method 1                   //  Linear /Constant Time
const double = arr2.map(num => num * 2)
//method 2                   //  Linear /Constant Time
const removeAndAddNewNumber = arr2.splice(1, 1, 5) 
//method 3                   //  Linear /Constant Time
const getSum = arr2.reduce((total, num) => total + num, 0) 
//method 4                   // Constant Time
for (const num of nums) {
 console.log(num * 2)
}
//method 5                   // Linear /Constant Time
const convertToString = arr2.join(' ')
//method 6                   //  Linear/Constant Time
const reversed = arr2.reverse()


Problem 13: For each one of these code blocks, please identify the time & space complexity and explanation of 
why it is.

Problem 1: 
function findFirstIndexOfNumber(number, array) {
 for (let i = 0; i < array.length; i++) {       // Linear or constant, insertion
 if (array[i] === number) {    // Linear, searching
 return i;                      // Constant, retrieving
 }
 }
 return -1                  //  Constant, retrieving
 }




Problem 2: 
function findEachIndexOfNumber(number,array) {
 let arrayOfIndexes = [];           
 array.forEach(function(element, index) { // Linear for searching
 if (element === number) {      // Linear for searching
 arrayOfIndexes.push(index);    // Linear or constant for insertion
 }
 });
 return arrayOfIndexes; // Constant because retrieving
 }


Problem 3: 
const array = [36, 14, 1, 7, 21]; 
function higherOrLower(array) {
 if (array[array.length -1 ] > array[0]) {   // Linear for searching
 return "Higher";                       // Constant for retrieving
 else if (array[array.length -1 ] < array[0]) { // Linear for searching
 return "Lower";                        // Constant for retrieving
 } else {
 return "Neither";                      // Constant for retrieving
 }
}


Problem 4: 
const array = [1,2,3,4,5,6,7,8]; 
function determineSumOfSequentialArray(array) {
 let sum = 0;    // Linear or constant 
 for (let i = 0; i < array.length; i++) {  // Linear for searching
 sum += array[i];   // Linear or constant for insertion
 }
 return sum;        // Constant for retrieving
}


Problem 5: 
const array = [1,2,3,4,5,6,7,8]; 
function determineSumOfSequentialArray(array) {
 return array.length * (array.length + 1)/2; // Constant for retrieving
}

Problem 6: 
function searchSortedArray(number, array, beginIndex = 0, endIndex = array.length - 1) {
 let middleIndex = Math.floor((beginIndex + endIndex)/2);
 if (array[middleIndex] === number) {      // Linear for searching
 return middleIndex;                        // Constant for retrieving
 } else if (beginIndex >= endIndex) {       // Linear for searching
 return -1;                                 // Constant for retrieving
 } else if (array[middleIndex] < number) {  // Linear for searching
 beginIndex = middleIndex + 1;              // Linear/Constant for insertion
 return recursiveBinarySearch(number, array, beginIndex, endIndex);
 } else if (array[middleIndex] > number) {  // Linear for searching
 endIndex = middleIndex - 1;            // Linear/Constant for removing
 return recursiveBinarySearch(number, array, beginIndex, endIndex);
 }  // Constant for retrieving
 }


Problem 7: 
const array1 = [3, 7, 9, 12, 15, 18, 32];
const array2 = [3, 3, 7, 41, 76];
function compareArrays(array1, array2) {
 let arrayOfPairs = [];        
 array1.forEach(function(e, i) {    // Linear for searching
 array2.forEach(function(e2, i2) {  // Linear for searching
 if (e === e2) {                    // Linear for searching
 arrayOfPairs.push([i, i2]);        // Linear/Constant for insertion
 }
 });
 });
 return arrayOfPairs;   //  Constant for retrieving
 
 Problem 8: 
function sortByValue(array){
 function swap(array, index1, index2){
 let temporaryValue = array[index1];
 array[index1] = array[index2];
 array[index2] = temporaryValue;
 }
 let count = 1;
 while (count < array.length) {     // Linear for searching
 let swapCount = 0;
 for (let i=0; i<array.length-count; i++) { // Linear for searching
 if (array[i] > array[i+1]) {       // Linear for searching
 swap(array, i, i+1);       // Linear/Constant for insertion or removing
 swapCount++;     // Linear/Constant for insertion
 }
 }
 count++;        // Linear/Constant for insertion
 }
 return array;                        // Constant for retrieving
 }

Problem 9: 
function returnDupes(array, array2) {
 let dupeArray = [];
 array.forEach(function(element) { // Linear for searching
 if (array2.includes(element)) {  // Linear for searching
 dupeArray.push(element);       // Linear/Constant for inserting
 }
 });
 return dupeArray;  // Constant for retrieving 
 }


Problem 10: 
function sumFilteredData(array) {
 return array.filter(function(element) {  // Linear for searching
 return ((element > 5) && (element < 20))  // Constant for retrieving
 }).reduce(function(valueToAdd, currentValue) { // Linear/Constant for removing
 return valueToAdd + currentValue; // Linear/Constant for either insertion
 }, 0);
 }