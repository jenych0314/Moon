---
layout: post
title: "php mysqli real escape string"
date: 2024-11-03
last_modified_at:
excerpt: "모의해킹 취업반 스터디 7기 3주차"
tags: [Post, TIL, Web, PHP]
comments: true
---

Object-oriented style
`public mysqli::real_escape_string(string $string): string`

Procedural style
`mysqli_real_escape_string(mysqli $mysql, string $string): string`
mysql과 connection할 때 string -> escape string으로 만들어준다
```php
$mysqli = mysqli_connect("localhost", "user", "pw", "table");

$sentence = "Hi. How are you?";

$query = sprintf("INSERT INTO English (sentence) VALUE ('$s')", $sentence);
$result = mysqli_query($mysqli, $query);

$query = sprintf("INSERT INTO English (sentence) VALUE ('$s')", mysqli_real_escape_string($mysql, $sentence));
$result = mysqli_query($mysqli, $query);
```

# 참고
1. https://www.php.net/manual/en/mysqli.real-escape-string.php
2. https://programming119.tistory.com/43