# postman-examples
一些常用的postman调试例子

### 常用的pre-request Script

#### github生成X-Hub-Signature
```javascript
var params = request.data;
var secret = 'your_secret';
var s_key = 'sha1=' + CryptoJS.HmacSHA1(JSON.stringify(JSON.parse(params)),secret).toString(CryptoJS.enc.Hex);
// var s_key = CryptoJS.HmacSHA1('123','sss').toString(CryptoJS.enc.Hex)
console.log(s_key)
pm.environment.set("X-Hub-Signature", s_key);
```
