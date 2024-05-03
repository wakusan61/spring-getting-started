# Spring REST API チュートリアルメモ

[Spring Boot REST API の作成 - 公式サンプル](https://spring.pleiades.io/guides/gs/rest-service)

## 実行手順

```bash
./gradlew bootRun
```

- ブラウザで http://localhost:8080/greeting にアクセスする。 
  - `{"id":1, "content":"Hello, Wrold!"}`
- http://localhost:8080/greeting?name=Java にアクセスする。
  - `{"id":2, "content":"Hello, Java!"}`

## Contrller の解説

`com.example.restservice.GreetingController.java`

- `@RestControler`
  - Http リクエストのコントローラのアノテーションでクラスにつける。
- `@GetMapping("/hoge")`
  - HTTP の GET リクエストを `/hoge` にマッピングする。
  - 他にも `@PostMapping` など、メソッドの数だけコンパニオンアノテーションがある。
- `@RequestParam(value = "name, defualt="World") String name`
  - クエリ文字列パラメータ name を name パラメータにバインドする。
  - name のクエリパラメータがない場合は World の defaultValue が使われる。

