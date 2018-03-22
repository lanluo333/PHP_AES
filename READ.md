使用PHP进行AES加密:
===============================
由于AES加密需要自己设置私钥，所以，如果是在tp5中，只要在配置文件app.php中定义aeskey的值即可(16位)，如果不是，则可以在此文件的构造函数中把$this->key的值写成16位的变量

注意:此处采用的是AES-128的方式进行加密，所以key值必须为16位的字符串

使用例子:

$data = [
  'name' => 'handsome',
  'id' => 1
];

$data = http_build_query($data);
//http_build_query()函数能把数组转换成name=handsome&id=1这样的形式

$Aes = new Aes('handsome333rui77');//此处的key是随便输入的16位字符串

var_dump($Aes->encrypt($data)); //结果为:9lRks1VZcWHbh/z8LQWFNHEYcelQ8DcTS/y0uTFNhcc=

var_dump($Aes->decrypt('9lRks1VZcWHbh/z8LQWFNHEYcelQ8DcTS/y0uTFNhcc=')); //解密,结果为:name=handsome&id=1

var_dump($Aes->encrypt_openssl($data));  //加密

var_dump($Aes->decrypt_openssl('9lRks1VZcWHbh/z8LQWFNHEYcelQ8DcTS/y0uTFNhcc='));  //解密


注：在PHP7中，Mcrypt已经被抛弃，所以，php7版本以上的推荐使用openss
