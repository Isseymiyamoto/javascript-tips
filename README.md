# javascript-tips
some javascript tips.. (especially for paiza)


## デフォルト関数

### 配列に対して用いる関数


### filter

・与えられたcallback関数を配列の各要素に対して一度ずつ呼び出し、callback が true と評価される値を返したすべての要素からなる新しい配列を生成

構文
```
let newArray = arr.filter(function(element, index, array){
    // 処理内容
});
```

重複を削除

```
var a = [1,2,3,3,2,2,5];

// 重複を削除したリスト
var b = a.filter(function (x, i, self) {
            return self.indexOf(x) === i;
        });

// 重複のみをリスト
var c = a.filter(function (x, i, self) {
            return self.indexOf(x) !== self.lastIndexOf(x);
        });

// 重複を検出したものを重複しないでリスト
var d = a.filter(function (x, i, self) {
            return self.indexOf(x) === i && i !== self.lastIndexOf(x);
        });
```

### map

・ 与えられた関数を配列の順番通りに、配列のすべての要素に対して呼び出し、その結果からなる新しい配列を生成する関数
・ 新しい配列を作成するため、返された配列を使わない場合、map を使うのはアンチパターン
・引数は、前から(currentVal(index番目の配列要素), index(callback関数の実行回数-1), array(mapする対象となっている配列))　からなり、currentValue以外はoptional型

構文
```
var new_array = arr.map(function callback(currentValue, index, array) {
    // 新しい配列の要素を返す
})
```


```javascript

const numArray = [1, 2, 3, 4];

const newArray = numArray.map((currentValue, index, array) => {
    console.log(array)   // [1,2,3,4] がコールバックが呼び出される回数出力される
    
    // 2番目の要素だけ何もせずにreturn
    if(index === 2){
        return currentValue * 10
    }
    
    return currentValue * 3;
});

// 期待される出力: [3, 6, 30, 12]
console.log(newArray);


```

### forEach

・与えられたコールバック関数を、配列の各要素に対して一度ずつ実行する
・for文を配列に対して用いているのと同じ？ただ途中でforEachループを完全に中断することはできない。例外処理は可能
・引数は、前から(currentVal(index番目の配列要素), index(callback関数の実行回数-1), array(mapする対象となっている配列))　からなり、currentValue以外はoptional型

```javascript

const items = ['item1', 'item2', 'item3']
const copyItems = [];

items.forEach(function(item){
    copyItems.push(item);
});

// itemsと全く同じものが出力される
console.log(copyItems);

```


### array

### apply

Math.maxで配列中の最大値を取得する
Math.max.apply(null, [1,4,8,7]); //=> 8

### reduce

https://qiita.com/chihiro/items/1047e40514a778c08baa

### sort


### join

・ 配列.join(引数)  
・ 配列(または配列風オブジェクト)の全要素を順に連結した文字列を新たに作成してreturnする  
・ 引数には配列の各要素を区切る文字列を指定する。省略された場合は、配列の要素は「,」で区切られる  

構文

```
array.join([separator])
```

```javascript

const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// output: "Fire,Air,Water"

console.log(elements.join(''));
// output: "FireAirWater"

console.log(elements.join('-'));
// output: "Fire-Air-Water"

```



### split

・String を指定した区切り文字列で分割することにより、文字列の配列に分割する
・引数には、(separetor(オプショナル型で、分割される部分の文字列を指定する。指定された文字列はさ分割の際に削除される))を取る

```javascript

const moji = "isseyMiyamoto"
const splits = moji.split("");

// 期待される出力： [i,s,s,e,y,M,i,y,a,m,o,t,o]
console.log(splits);

const splits2 = moji.split("m");

// 期待される出力：[isseyMiya, oto];
console.log(splits2);



```


### splice

・spliceメソッドは、 既存の要素を取り除いたり、置き換えたり、新しい要素を追加したりすることで、配列の内容を変更する

構文
```
Array.splice(startIndex, deleteCount, insertWord);

startIndex: 削除したい要素のindex番号
deleteCount: 削除したい要素から何個の要素を削除するか
insertWord: 何個でも増やす事ができる。startIndex番号目の要素の手前に挿入される
```

```javascript

let myFish = ['angel', 'clown', 'mandarin', 'sturgeon']
let removed = myFish.splice(2, 0, 'drum')

// myFish は ["angel", "clown", "drum", "mandarin", "sturgeon"] 
// removed は [], どの要素も取り除かれていない (空配列) 

let myFish = ['angel', 'clown', 'drum', 'mandarin', 'sturgeon']
let removed = myFish.splice(3, 1)

// removed は ["mandarin"]
// myFish は ["angel", "clown", "drum", "sturgeon"]

```


### push

### indexOf

・引数に与えられた内容と同じ内容を持つ配列要素の内、最初のものの添字をreturn
・存在しない場合は、-1をreturn
・引数は、(searchElement(検索する配列要素))

構文
```
arr.indexOf(searchElement)
```

```javascript

const array = [1, 2, 3, 1];
const result = array.indexOf(1);
console.log(result);     // => 0

// groupに自分がいるか検索
  function belongToGroup(groupNum, myNum) {
    const groupMembers = groupMembersArray[groupNum - 1];
    const result = groupMembers.indexOf(myNum);
    if (result === -1) {
      return false;
    } else {
      return true;
    }
  }
});

```

### 型キャスト関数

### Number()
Number型に変換

### parseInt()
### String()


### Math

```javascript
//四捨五入
Math.round(<数値>)
//ex1) Math.round(123.456) // 出力：123
//ex2) Math.round(123.567) // 出力：124
//切り上げ
Math.ceil(<数値>)
//ex1) Math.ceil(123.456) // 出力：124
//ex2) Math.ceil(123.567) // 出力：124
//切り捨て
Math.floor(<数値>)
//ex1) Math.floor(123.456) // 出力：123
//ex2) Math.floor(123.567) // 出力：123

// ルート計算
Math.sqrt()
ex) Math.sqrt(9) // output is 3

// 引数が整数か否かをBool値でreturn
Number.isInteger()
ex) Number.isInteger(4) // output is true

```
