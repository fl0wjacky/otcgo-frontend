### 蓝鲸淘前端部分
目前只包含使用的库部分

说明：
- aes.js [引自https://code.google.com/archive/p/crypto-js/](https://code.google.com/archive/p/crypto-js/)
- biginteger.js [引自https://github.com/silentmatt/javascript-biginteger，有改动](https://github.com/silentmatt/javascript-biginteger)
- jsrsasign-latest-all-min.js [引自https://github.com/kjur/jsrsasign](https://github.com/kjur/jsrsasign)
- sha256.js [引自https://github.com/Caligatio/jsSHA](https://github.com/Caligatio/jsSHA)
- Base58.js [引自https://github.com/45678/Base58](https://github.com/45678/Base58/)
- LJSign.js 参考自https://pypi.python.org/pypi/ecdsa

引用：
```
<script src="js/biginteger.js"></script>
<script src="js/aes.js"></script>
<script src="js/jsrsasign-latest-all-min.js"></script>
<script src="js/sha256.js"></script>
<script src="js/Base58.js"></script>
<script src="js/LJSign.js"></script>
```
调用示例：
WIF私钥生成Hex私钥：
```
var wif = 'Kzyj3dNv2vdwUf4MwmD7nKqoe121xkirE6LNStGdNv2rf6pNVGdx';
var prvhex = ljWifkeyToHexkey(wif);
console.log(prvhex);
//"7027b47d1a599df85f9089b63cf8ddfff13df5a8819649074bc189127d15106c"
```
Hex私钥生成公钥
```
var pubhex = ljPrikeyToPubkey(prvhex);
console.log(pubhex);
//"0483cdbc3f4d2213043c19d6bd041c08fbe0a3bacd43ef695500a1b33c609a9e8a180eee2ada65ddb65154863c57bac9ab1b89a61593235991d5fb6f627c0cadbd"
```
生成签名
```
var msg = 'aabbccdd';
var sighex = ljSign(prvhex, msg);
console.log(sighex);
//"a8a3f1875b548831ecfd8b7d31f4a6375d7891f9233863fc5dee04f7084f701da787b073f1303125632971d9d0ffc69ba555813f556aa6733f79574424c85239"
```
