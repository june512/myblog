---
title: "AWS"
date: 2020-05-19T17:29:48+09:00
---
# Ŭ������ ����
```
aws ���� Ȩ���������� ���̵������ putty�� �����ϱ� ������ ���.
putty�� ����ϴ� ������ ������ �����ϴ� ����� �������� �������� �����ؼ� ����ϱ� �����̴�.
putty ��ġ : <https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html>
```
## 1. Ű ����
.pem Ȯ������ Ű�� .ppkȮ������ private key�� �����ϴ� �����̴�.

putty�� ���ռ�ġ�ϸ� �����ִ� puttygen�� �̿��Ѵ�.

![key_1](https://user-images.githubusercontent.com/65329769/82172214-8811ac80-9904-11ea-87a3-6e7a4804e55d.jpg)

Load Ŭ�� - ��� ���� - �Ʊ� ������� .pem Ű ����

![key_2](https://user-images.githubusercontent.com/65329769/82172307-c1e2b300-9904-11ea-9980-1c99159fc8cd.jpg)

Save private key�� ����. (�̸��� �Ȱ���)



## 2. ���� �� ����
<https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/putty.html> �� ����

#### ȣ��Ʈ ���� ubuntu@(public dns)
#### SSH ��Ʈ22
#### SSH-Auth-�Ʊ� ���� .ppk Ű �ҷ�����


# �� ����(����ġ) ��ġ

putty�� �� �ܼ�â�� �̰͵��� �Է�
```
sudo apt-get update

sudo apt-get update sudo apt-get install apache2
```

![993F4C4A5B5D39EA2F](https://user-images.githubusercontent.com/65329769/82172488-433a4580-9905-11ea-9329-481702b86e6c.jpg)

#### ��ó : <https://woodforest.tistory.com/279>
