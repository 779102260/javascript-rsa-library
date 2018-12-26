>The Library only support rsa encrypt . 
>The code author is [Tom Wu](http://www-cs-students.stanford.edu/~tjw/jsbn/) , all i did was just put them together !

此rsa库仅支持加密，由jsbn.js + prng4.js + rng.js + rsa.js + base64.js构成

# Usage

```js
import RSAKey,{hex2b64,linebrk} from './rsa.js';
//key Modulus (hex) 模数，并非公钥。
const    key='a5261939975948bb7a58dffe5ff54e65f0498f9175f5a09288810b8975871e99af3b5dd94057b0fc07535f5f97444504fa35169d461d0d30cf0192e307727c065168c788771c561a9400fb49175e9e6aa4e23fe11af69e9412dd23b0cb6684c4c2429bce139e848ab26d0829073351f4acd36074eafd036a5eb83359d2a698d3';
//'10001'是指数，公钥分解指定的，一般默认都是10001。
const encrypt = new RSAKey();
encrypt.setPublic(key,'10001'); 
let encrypted=encrypt.encrypt(content);
let encryptedBase64=linebrk(hex2b64(encrypted), 64);

console.log(encryptedBase64);
```
注：如果你只有RSA公钥可分解为模数和指数，[在线工具](http://tool.chacuo.net/cryptrsakeyparse)。