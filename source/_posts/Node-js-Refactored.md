---
title: Node.js Refactored
date: 2019-10-10 11:43:07
tags: Node.js,Javascript
---

In the past two years I didn't use Node.js during my work. Before I used Coffeescript for many years. As ES6 grows and lots of new features added. I will make a list what I need to revise.


## MapReduce in Javascript

Here is the paper the google published [MapReduce: Simplified Data Processing on Large Clusters](https://ai.google/research/pubs/pub62)

javascript array has two methods "map" and "reduce", use this can easily make you code clean and readable. Beware about the arguments the methods takes.
see <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map>

## Pickups

### strings
news in string, `` for multilines strings. ${} can use in `` . but only for the environment that support ES6+.

string can't change. as others languages.

### array

1. splice actually I don't like this method. It can do so much things that make the code hard to read.

    ```
    var arr = ['Microsoft', 'Apple', 'Yahoo', 'AOL', 'Excite', 'Oracle'];
    // 从索引2开始删除3个元素,然后再添加两个元素:
    arr.splice(2, 3, 'Google', 'Facebook'); // 返回删除的元素 ['Yahoo', 'AOL', 'Excite']
    arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
    // 只删除,不添加:
    arr.splice(2, 2); // ['Google', 'Facebook']
    arr; // ['Microsoft', 'Apple', 'Oracle']
    // 只添加,不删除:
    arr.splice(2, 0, 'Google', 'Facebook'); // 返回[],因为没有删除任何元素
    arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
    ```

1. concat method will auto break the first levels array. and return a new arry. the origin one didn't change.

1.  objects

    1. try don't use a no validate variable name as a objects key. becuase you have to visit it use ''
    1. we can use "in" to check if an object has a property. but this still works for the property the inherit. eg:
        ```
        'toString' in [obj]; //true
        ```
    1. hasOwnProperty check is the property is it's own.

1. Loop
     for ... in can loop an object's all keys, use hasOwnProperty to filter unwanted.
     if it's an array, the key is index.

     for ... of only iterator the elements in the collection.

1. Closure As I understand, closure means all the args it used can't be access be out, so it's close.
    1. care about the args in a loop you used in a function. eg:
        ```
        function count() {
            var arr = [];
            for (var i=1; i<=3; i++) {
                arr.push(function () {
                    return i * i;
                });
            }
            return arr;
        }

        var results = count();
        var f1 = results[0]; //16
        var f2 = results[1]; //16 
        var f3 = results[2]; //16
        f1();//16

        because i changed to 4 when you run f1(),f2(),f3()
        ```



