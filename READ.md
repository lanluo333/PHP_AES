ʹ��PHP����AES����:
===============================
����AES������Ҫ�Լ�����˽Կ�����ԣ��������tp5�У�ֻҪ�������ļ�app.php�ж���aeskey��ֵ����(16λ)��������ǣ�������ڴ��ļ��Ĺ��캯���а�$this->key��ֵд��16λ�ı���

ע��:�˴����õ���AES-128�ķ�ʽ���м��ܣ�����keyֵ����Ϊ16λ���ַ���

ʹ������:

$data = [
  'name' => 'handsome',
  'id' => 1
];

$data = http_build_query($data);
//http_build_query()�����ܰ�����ת����name=handsome&id=1��������ʽ

$Aes = new Aes('handsome333rui77');//�˴���key����������16λ�ַ���

var_dump($Aes->encrypt($data)); //���Ϊ:9lRks1VZcWHbh/z8LQWFNHEYcelQ8DcTS/y0uTFNhcc=

var_dump($Aes->decrypt('9lRks1VZcWHbh/z8LQWFNHEYcelQ8DcTS/y0uTFNhcc=')); //����,���Ϊ:name=handsome&id=1

var_dump($Aes->encrypt_openssl($data));  //����

var_dump($Aes->decrypt_openssl('9lRks1VZcWHbh/z8LQWFNHEYcelQ8DcTS/y0uTFNhcc='));  //����


ע����PHP7�У�Mcrypt�Ѿ������������ԣ�php7�汾���ϵ��Ƽ�ʹ��openss
