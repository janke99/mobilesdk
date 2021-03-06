---
weight: 11
title: API Reference
---

# ETH钱包




## 创建新的NEO钱包

> 创建新的NEO钱包:


```java
package com.inwecrypto.test

public class App {
    public static void main(String args[]) {
        ethmobile.Wallet wallet = ethmobile.new_();
    }
}
```
```objc
    
```

#### 请求参数

Parameter | Default | Description
--------- | ------- | -----------


## 通过读取web3 keystore字符串创建钱包

> 读取keystore:

```java
package com.inwecrypto.test

public class App {
    public static void main(String args[]) {
        ethmobile.Wallet ethwallet = ethmobile.fromKeyStore("xxxxxx","xxxxx");
    }
}
```
> keystore的格式类似下面的json代码：

```json
{
    "version": 3,
    "id": "1b3cb7fc-306f-4ec3-b753-831cb9e18984",
    "address": "00e773ad3fa1481bc4222277f324d57f35f06b60",
    "crypto": {
        "ciphertext": "423abc4fea2f1f58543b456f9a67f60eb7be076a79471d284d2777c1ce5ee2cd",
        "cipherparams": {
            "iv": "a737c70e4541a9eb053a49e9103d7ccc"
        },
        "cipher": "aes-128-ctr",
        "kdf": "pbkdf2",
        "kdfparams": {
            "dklen": 32,
            "salt": "0de73ba9540afa6424f05d159575a665da3aefa751cd7c56fc5dd87aeac4ea6b",
            "c": 65536,
            "prf": "hmac-sha256"
        },
        "mac": "53b2cf7744e91d2718f9aa586dac8c5fb647b3b912b5c4ba3c1eafd7a99346e3"
    }
}
```

### 请求参数


Parameter | Type | Description
--------- | ---- | -----------
keystore | string | keystore json 字符串
password | string | keystore 秘钥

## 通过助记词创建钱包

> 读取助记词:

```java
package com.inwecrypto.test

public class App {
    public static void main(String args[]) {
        ethmobile.Wallet ethwallet = ethmobile.fromMnemonic("xxxxxx","zh_CN");
        ethwallet.Transfer("","","","","")
    }
}
```

### 请求参数


Parameter | Type | Description
--------- | ---- | -----------
mnemonic | string | 空格分割的助记词字符串
lang | string | 助记词语言，当前支持 zh_CN ， en_US

## 通过私钥创建钱包

> 读取助记词:

```java
package com.inwecrypto.test

public class App {
    public static void main(String args[]) {
        ethmobile.Wallet ethwallet = ethmobile.fromPrivateKey("xxxxxx");
        ethwallet.Transfer("","","","","")
    }
}
```

### 请求参数


Parameter | Type | Description
--------- | ---- | -----------
privateKey | string | hex形式私钥


## 全局资产转账（ETH)

> 转账:

```java
package com.inwecrypto.test

public class App {
    public static void main(String args[]) {
        ethmobile.Wallet ethwallet = ethmobile.fromMnemonic("xxxxxx","zh_CN");
        ethwallet.Transfer("","","","","")
    }
}
```


### 请求参数


Parameter | Type | Description
--------- | ---- | -----------
nonce | string | 服务器获取的nonce
to | string | 助记词语言，当前支持 zh_CN ， en_US
amount | string | 助记词语言，当前支持 zh_CN ， en_US
gasPrice | string | 燃料费价格
gasLimits | string | 燃料最高限额



## ERC20资产转账

> 转账:

```java
package com.inwecrypto.test

public class App {
    public static void main(String args[]) {
        ethmobile.Wallet ethwallet = ethmobile.fromMnemonic("xxxxxx","zh_CN");
        ethwallet.TransferERC20("","","","","","")
    }
}
```


### 请求参数


Parameter | Type | Description
--------- | ---- | -----------
contract | string | 合约地址
nonce | string | 服务器获取的nonce
to | string | 助记词语言，当前支持 zh_CN ， en_US
amount | string | 助记词语言，当前支持 zh_CN ， en_US
gasPrice | string | 燃料费价格
gasLimits | string | 燃料最高限额