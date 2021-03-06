## Composer
Composer는 PHP 소프트웨어와 필요 라이브러리의 의존성을 관리하기 위한 표준 포맷을 제공하는 PHP ==의존성 관리도구==이다.

*의존성 관리도구* : 프로젝트 내에 포함된 라이브러리들의 의존성을 관리해주는 소프트웨어


## Composer 설치
php 5.3.2 이상

로컬 설치
```sh
curl -sS https://getcomposer.org/installer | php
```
```sh
php -r "readfile('https://getcomposer.org/installer');" | php
```
<br>


글로벌 설치
```sh
curl -sS https://getcomposer.org/installer | php
mv composer.phar /usr/local/bin/composer
```


## 의존성 선언
composer.json 파일에 의존 라이브러리 목록을 작성

```text
{
    "require": {
        "monolog/monolog": "1.2.*" //설치할 라이브러리의 이름과 버전
    }
}
```

## 자동 불러오기
아래 코드를 코드에 추가하면 composer.json에 선언한 라이브러리 들이 자동으로 불러와진다.
```text
require 'vendor/autoload.php';
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5MzQwMzcwMiwxMzQzMTY3Nzg5LC01NT
cyMjMxMjRdfQ==
-->