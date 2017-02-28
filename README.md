# the-stop-watch
create a basic stop watch using operators such as .interval | .switchMapTo | .scan

## my refs
http://reactivex.io/documentation/operators/scan.html  
https://egghead.io/lessons/rxjs-updating-data-with-scan#/tab-transcript

examining the .scan() operator
```js
startInterval$
  .scan((acc)=>{
    debugger;
    return {count: acc.count + 1}
  },{count: 0})
  .subscribe((x)=>console.log(x))
  ```
  
The proper way to gather and collect data in RxJS is to use the scan operator.

+Scan works just like reduce in JavaScript arrays. 
+We take a function and initializer. 
+Our initializer is just going to be a count of zero or an object with a count of zero. 
+Then, that comes into this function as an accumulator.
```js
.scan((acc)=>{},0)
.scan((acc)=>{},{count: 0})
```


When this function is called, I get this accumulator as this first argument. We'll just go ahead and return a new object with a property called "count," which is accumulator.count plus one. For something more advanced, you'll probably use object assign, but we just have one property for now.

I'll go ahead and save. I'll hit start. We go one, two, three. I'll hit stop, and then hit start again, and re-continue five, six, seven. This now reads as clicking a start button, which switches to a timer that can stop when you click stop.

Then, each time a new interval is pushed or you get a new tick, we start with this value which is this accumulator here.

Then we run this function, which is just going return an object with a count on it. It's going to take that previous accumulator find account property, add one. Then is going to be pushed into my subscribe and logged out...

![alt text](http://reactivex.io/documentation/operators/images/scanSeed.js.png)
