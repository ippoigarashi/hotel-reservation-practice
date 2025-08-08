# 第2章 Spring Bootプロジェクトの作成・実行手順

---

## 1. Spring Bootプロジェクトの新規作成

1. [Spring Initializr](https://start.spring.io/) にアクセス
2. 以下の設定例でプロジェクトを作成
   - Project: Gradle Project または Maven Project
   - Language: Java
   - Spring Boot: 最新安定版
   - Group: com.example
   - Artifact: hotel-reservation
   - Dependencies: Spring Web, Spring Data JPA, H2 Database など
3. [Generate]ボタンでzipファイルをダウンロードし、解凍して `src/` フォルダに配置

## 2. VSCodeでプロジェクトを開く

1. VSCodeで `src/hotel-reservation` フォルダを開く
2. 必要に応じてJava Extension Packをインストール

## 3. プロジェクトのビルド・実行

1. ターミナルで以下のコマンドを実行
   - Gradle: `./gradlew bootRun`
   - Maven: `./mvnw spring-boot:run`
2. ブラウザで `http://localhost:8080` にアクセスし、起動確認

## 4. サンプルAPIの追加

1. `src/main/java/com/example/hotelreservation/controller/HelloController.java` を作成
2. 以下のサンプルコードを追加

```java
package com.example.hotelreservation.controller;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloController {
    @GetMapping("/hello")
    public String hello() {
        return "Hello, Hotel Reservation!";
    }
}
```

3. 再度アプリを起動し、`http://localhost:8080/hello` で動作確認

---

## 参考
- Spring公式: https://spring.io/projects/spring-boot
- VSCode Java拡張: https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack
