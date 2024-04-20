[](curl.md)
# curl
URLを利用しクライアントからサーバへリクエストしてデータを取得、送信するコマンド。オプションでHTTPメソッドを明示的に指定しない場合は、GETリクエストを送信する。

  実行例 [](変更しない)
  
  ```
  curl http://www.example.com
  ```

  実行結果 [](変更しない)

  ```
  <!doctype html>
  <html>
  <head>
      <title>Example Domain</title>

      <meta charset="utf-8" />
      <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <style type="text/css">
      body {
          background-color: #f0f0f2;
          margin: 0;
          padding: 0;
          font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
          
      }
      div {
          width: 600px;
          margin: 5em auto;
          padding: 2em;
          background-color: #fdfdff;
          border-radius: 0.5em;
          box-shadow: 2px 3px 7px 2px rgba(0,0,0,0.02);
      }
      a:link, a:visited {
          color: #38488f;
          text-decoration: none;
      }
      @media (max-width: 700px) {
          div {
              margin: 0 auto;
              width: auto;
          }
      }
      </style>    
  </head>

  <body>
  <div>
      <h1>Example Domain</h1>
      <p>This domain is for use in illustrative examples in documents. You may use this
      domain in literature without prior coordination or asking for permission.</p>
      <p><a href="https://www.iana.org/domains/example">More information...</a></p>
  </div>
  </body>
  </html>
  ```

### オプション一覧

- **-X [http method]**

  引数 `[http method]` で指定したHTTPメソッドでリクエストを行うオプション。主に使用するメソッドは以下の通り。

  - GET: リソースの取得
  - POST: リソースの作成など
  - PUT: リソースの更新、作成
  - DELETE: リソースの削除

  実行例 [](変更しない)

  ```
  curl -X GET http://www.example.com
  ```

  実行結果 [](変更しない)

  ```
  <!doctype html>
  <html>
  <head>
      <title>Example Domain</title>

      <meta charset="utf-8" />
      <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <style type="text/css">
      body {
          background-color: #f0f0f2;
          margin: 0;
          padding: 0;
          font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
          
      }
      div {
          width: 600px;
          margin: 5em auto;
          padding: 2em;
          background-color: #fdfdff;
          border-radius: 0.5em;
          box-shadow: 2px 3px 7px 2px rgba(0,0,0,0.02);
      }
      a:link, a:visited {
          color: #38488f;
          text-decoration: none;
      }
      @media (max-width: 700px) {
          div {
              margin: 0 auto;
              width: auto;
          }
      }
      </style>    
  </head>

  <body>
  <div>
      <h1>Example Domain</h1>
      <p>This domain is for use in illustrative examples in documents. You may use this
      domain in literature without prior coordination or asking for permission.</p>
      <p><a href="https://www.iana.org/domains/example">More information...</a></p>
  </div>
  </body>
  </html>
  ```

- **-O**

  指定したURLからファイルをダウンロードし、そのファイルの名前をそのまま保存するオプション。

  実行例 [](変更しない)

  ```
  curl -O https://example.com/example.jpg
  ```

  実行結果 [](変更しない)

  ```
    % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  100  1256  100  1256    0     0   2129      0 --:--:-- --:--:-- --:--:--  2132
  ```

  現在のディレクトリに`example.jpg`が保存される。

  実行結果 [ls](変更しない)

  ```
  user@localhost:~$ ls
  example.jpg
  ```

- **-o [file_path]**

  引数 `[file_path]` で指定した場所、ファイル名でリクエストの結果を保存するオプション。

  実行例 [](変更しない)

  ```
  curl -o ./hoge.txt http://www.example.com
  ```

  実行結果 [](変更しない)

  ```
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  100  1256  100  1256    0     0   4405      0 --:--:-- --:--:-- --:--:--  4391
  ```

  現在のディレクトリに`hoge.txt`が保存される。

  実行結果 [](変更しない)

  ```
  user@localhost:~$ ls
  hoge.txt

  user@localhost:~$ cat hoge.txt
  <!doctype html>
  <html>
  <head>
      <title>Example Domain</title>

      <meta charset="utf-8" />
      <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <style type="text/css">
      body {
          background-color: #f0f0f2;
  *** 以下省略 ***
  ```

- **-I / --head**

  HTTPレスポンスヘッダーを取得するオプション。

  実行例 [](変更しない)

  ```
  curl -I http://www.example.com
  ```

  実行結果 [](変更しない)

  ```
  HTTP/1.1 200 OK
  Content-Encoding: gzip
  Accept-Ranges: bytes
  Age: 251548
  Cache-Control: max-age=604800
  Content-Type: text/html; charset=UTF-8
  Date: Sat, 20 Apr 2024 07:57:49 GMT
  Etag: "3147526947+gzip"
  Expires: Sat, 27 Apr 2024 07:57:49 GMT
  Last-Modified: Thu, 17 Oct 2019 07:18:26 GMT
  Server: ECAcc (sac/2533)
  X-Cache: HIT
  Content-Length: 648
  ```

- **-v / --verbose**

  ネットワークリクエストとレスポンスの詳細な情報を表示するオプション。
  - リクエストライン（HTTPメソッド、URL、HTTPバージョン）
  - リクエストヘッダー
  - レスポンスライン（HTTPステータスコード、メッセージ）
  - レスポンスヘッダー
  - レスポンスボディ（オプションで表示）

  実行例 [](変更しない)

  ```
  curl -v http://www.example.com
  ```

  実行結果 [](変更しない)

  ```
  *   Trying 93.184.215.14:80...
  * Connected to www.example.com (93.184.215.14) port 80 (#0)
  > GET / HTTP/1.1
  > Host: www.example.com
  > User-Agent: curl/7.81.0
  > Accept: */*
  > 
  * Mark bundle as not supporting multiuse
  < HTTP/1.1 200 OK
  < Accept-Ranges: bytes
  < Age: 253816
  < Cache-Control: max-age=604800
  < Content-Type: text/html; charset=UTF-8
  < Date: Sat, 20 Apr 2024 08:35:37 GMT
  < Etag: "3147526947"
  < Expires: Sat, 27 Apr 2024 08:35:37 GMT
  < Last-Modified: Thu, 17 Oct 2019 07:18:26 GMT
  < Server: ECAcc (sed/5906)
  < Vary: Accept-Encoding
  < X-Cache: HIT
  < Content-Length: 1256
  < 
  <!doctype html>
  <html>
  <head>
      <title>Example Domain</title>

      <meta charset="utf-8" />
      <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <style type="text/css">
      body {
          background-color: #f0f0f2;
          margin: 0;
          padding: 0;
          font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
          
      }
      div {
          width: 600px;
          margin: 5em auto;
          padding: 2em;
          background-color: #fdfdff;
          border-radius: 0.5em;
          box-shadow: 2px 3px 7px 2px rgba(0,0,0,0.02);
      }
      a:link, a:visited {
          color: #38488f;
          text-decoration: none;
      }
      @media (max-width: 700px) {
          div {
              margin: 0 auto;
              width: auto;
          }
      }
      </style>    
  </head>

  <body>
  <div>
      <h1>Example Domain</h1>
      <p>This domain is for use in illustrative examples in documents. You may use this
      domain in literature without prior coordination or asking for permission.</p>
      <p><a href="https://www.iana.org/domains/example">More information...</a></p>
  </div>
  </body>
  </html>
  * Connection #0 to host www.example.com left intact
  ```