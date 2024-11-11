---
layout: post
title: "[PHP] PHP에서 SQL 연결하기"
date: 2024-10-23
last_modified_at: 2024-11-11
excerpt: "모의해킹 취업반 스터디 7기 2주차"
tags: [WEB, PHP, DATABASE]
comments: true
---

database: 데이터를 저장한다
was <-> db

php에서 sql 문구를 어떻게 작성하느냐?
was-db 연결 = php와 mysql 연동시키기
<?php
    define('DB_SERVER', 'localhost(ip)');
    define('DB_USERNAME', 'admin');
    define('DB_PASSWORD', 'student1234');
    define('DB_NAME', 'test');

    $db_conn = mysqli_connect(DB_SERVER, DB_USERNAME, DB_PASSWORD, DB_NAME);

    if ($db_conn) {
        echo "DB Connect OK";
    } else {
        echo "DB Connect Fail";
    }

    $sql = "select * from test";
    $result = mysqli_query($db_conn, $sql);
    
    echo $result;
    var_dump($result);

    $row1 = mysqli_fetch_array($result); // 무조건 순서대로 한 줄씩 가져온다 readline 같은 느낌으로
    $row2 = mysqli_fetch_array($result);
    $row3 = mysqli_fetch_array($result);

    echo "Name: " . $row1['name']; // string1 . string2 => string1string2
    // 약간 python dictionary 같은 느낌

    if($_POST['userpass'] == $db_pass) {
        login OK
    }
?>

was에 db의 id와 pw가 무조건 들어있다
web shell을 까면 db 추측을 먼저 해야 한다
hash로 못 숨기나?
php 함수일 때는 $ 안 붙이고 모든 변수 앞에서는 $ 붙이는 듯
선언을 했든 안 했든
디스크립토
descrypto