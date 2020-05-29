# javascript-tips
write down some javascript tips.. (especially for paiza)


## デフォルト関数

### 配列に対して用いる関数

#### map

・ 与えられた関数を配列の順番通りに、配列のすべての要素に対して呼び出し、その結果からなる新しい配列を生成する関数
・ 

構文
```
var new_array = arr.map(function callback(currentValue[, index[, array]]) {
    // 新しい配列の要素を返す
}[, thisArg])
```


#### array


#### join

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



#### split

#### forEach


#### push

### 型キャスト関数

#### Number()
#### parseInt()
#### String()

