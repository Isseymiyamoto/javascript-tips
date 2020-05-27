# javascript-tips
write down some javascript tips.. (especially for paiza)


## デフォルト関数

### 配列に対して用いる関数

#### map


#### array


#### join

・ 配列.join(引数)  
・ 配列(または配列風オブジェクト)の全要素を順に連結した文字列を新たに作成してreturnする  
・ 引数には配列の各要素を区切る文字列を指定する。省略された場合は、配列の要素は「,」で区切られる  

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


#### push

### 型キャスト関数

#### Number()
#### parseInt()
#### String()

