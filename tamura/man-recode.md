[](man-recode.md)
# man-recode
マニュアルページ（ manページ ）を別のエンコーディングに変換するためのユーティリティ。
ファイル名から各ページに対して適切な入力エンコーディングを推測して変換することもある。これは、レガシーな文字コードが使用されているマニュアルページの多くを共通のエンコード方法（ 一般に UTF-8 ）で変換する場合で有用である。このプログラムは各ページに対して`man --recode` や `manconv` を実行するよりもはるかに高速である。

マニュアルページの最初の行で以下のようなエンコーディング宣言が見つかると、その宣言が入力エンコーディングとして使われる。そうでない場合は、入力エンコーディングはファイル名から推測される。

マニュアルページの先頭に書かれるエンコーディング宣言は通常は以下の形式をとる：

```
'\"-*- coding: UTF-8 -*-
```

\**マニュアルページプリプロセッサ* も宣言する場合：

```
'\" t -*- coding：ISO-8859-1 -*-
```

(\* マニュアルページプリプロセッサ : マニュアルページ（manページ）の作成や処理を補助するためのツールやプログラムのこと。ソースコードを構造化された形式に変換し、適切なマークアップやフォーマットを適用する役割を果たす。)

上記のエンコーディング宣言を変換したいマニュアルページの冒頭に書き加えたのち、`man-recode` コマンドを実行することでエンコーディング方法を変更してマニュアルページを作成できる。

実行例 []()
```
man-recode -t shift_jis --in-place touch.1.gz
```

実行結果 [/usr/share/man/man1]()
```
// 変更前 touch.1.gz(UTF-8) 
// user@localhost:/usr/share/man/man1$ man ./touch.1.gz

TOUCH(1)                         User Commands                        TOUCH(1)

NAME
       touch - change file timestamps

SYNOPSIS
       touch [OPTION]... FILE...

DESCRIPTION
       Update  the  access  and modification times of each FILE to the current
       time.

       A FILE argument that does not exist is created empty, unless -c  or  -h
       is supplied.

       A  FILE  argument  string of - is handled specially and causes touch to
       change the times of the file associated with standard output.

       Mandatory arguments to long options are  mandatory  for  short  options
       too.

       -a     change only the access time

       -c, --no-create
              do not create any files
... 
```
以上のように正常なマニュアルページが表示される

実行結果 [~/man-recode]()
```
// 変更前 touch.1.gz(shift-jis) 
// user@localhost:~/man-recode$ man ./touch.1.gz

^B^C�Vmo�6��_q󗥘�$N�u�Z���mb��"��(��D�"eG��;�/�
tb�’����1
��"|�Gx^Fat����:�\[uFFFD]UU����y����^CĦ��S��w�%   ����h’��
\[uFFFD]�dp?                          ���^L��gB�%�*��T!�Ei���q2�‐Ƌ
|?xZ��ew:�����l�Ο�0^DR",B    kG���^F!&?H�.....�$�)�E��q�J:a��^L��,x(��L��ci‐
j%P�D�*|��^D���^Dy��X#��Jj�7B67��E����       ^G�A}m�e(q%��(]ӅZ��y�~\[uFFFD]Ƙ��2<^Dx��e�+��؉u��k�+����I��m)c%��bQ[�÷<U+0099>�m^E�ϐ�a�A]�q�\[uFFFD].Є�0�+k��’�3��](drC�p�����b^?/��lf*���!��^B�WP�m‘Fc�G}�
7�L]_��6(�~b��^�
���A79�M��{��"��’7^L�����%@,(l��N���u����O�Z#;�7^Gy��^Da�^?:�E���y�٦X�\[u0150]+���%���J^Bn�   F�ֹ�^B�6x��|1R����@:�F���Q�ŏz�B�W�i’��5S^C�����E�O���hp?cOOWWϏ�����a��Sh��ϭ�<��2�}TG4‘��H3��^Gt���.�^EA�.�^C��V���ٗ�^C~wj\[uFFFD]��l�G
\[uFFFD]                                                        i
3��‐s��z���������bCH��Z.�^C�V�^G^Hv4����N8�xO^G�t(�y�^CL��V_T������
�d����3��W)K�^D�I�+Qf�N�~�PFK���%�Pr�.޷�‘5�C0��ܹ���}�4O�
i�Q�YXr��:�Zw��’����u�.~��.�o{pz���C��Ї���)��}���H‐_DY]�D4�‘p�
�[��P;�)(��     S^E㈩�88Y���#�������ҙ�[)�v1��7~,w��ћ�F�Xa�)�w�.��5�y,�J���G;��*E٫b��ɐ�q�����D�P
��^F�j�3�A�V5�����ݺ�oX^E�D��                   ��^Ce��N�#�r������5�W
5������q�T......�1���n0���?K�]����O^C�^B��"q>�M�����͢�~��D7�T�ʜ+m��l�݆k]��Z�Y��‐�����ه
U�\[uFFFD]��h^B�Jh�{z��5������ee�ƙ�vq>d     c������(�2eS�u�‘yz[��5A|�F......צ��ƺ0�qܩXj�7����o}����=�/       ��_b�v��^מ��<�\[uFFFD]^?^H9��J�$׻^B�15/pc���jS^DD.....mŐh�7��d
_^F��‘=vw%dM�RV^E���ض[�F0�[L;�5��5j�w��]���P9O����^D�(��\[uFFFD]�o’{�7�H���^G���v�A

 Manual page touch.1.gz line 1/19 (END) (press h for help or q to quit)
```
以上のように文字化けが発生してしまう。


### オプション一覧

- **-t, --to-code=CODE**

  出力のエンコーディング方法を指定するオプション。この指定は必須であるため、忘れるとコマンドが実行できない。

  上で既に実行例を出しているため実行例は省略する。

- **-d, --debug**

  デバッグ情報を出すオプション。

  実行例 []()
  ```
  man-recode -d -t shift_jis --in-place touch.1.gz
  ```

  実行結果 []()
  ```
  loading seccomp filter (permissive: 0)
  guessed input encoding UTF-8 for touch.1.gz
  loading seccomp filter (permissive: 0)
  seccomp already enabled
  trying encoding UTF-8 -> shift_jis//IGNORE
  stem: touch.1, basename: touch.1.gz
  ```

  この場合は、UTF-8 でエンコーディングされることが予想されるファイルであり、そのファイルを無理やり shift_jis でエンコーディングしようとしたことが読み取れる。

  `//IGNORE` は変換できない文字をそのままにしておくオプションであるらしい。

- **--in-place**

  入力ファイルをその場で上書きするオプション。圧縮拡張子が削除される。
  
  上で既に実行例を出しているため実行例は省略する。

- **--suffix=SUFFIX**

  出力ファイル名に付加する接尾辞を引数（ `SUFFIX` ）として指定することで、その接尾辞でファイルを作成するオプション。

  実行例 []()

  ```
  man-recode -t shift_jis --suffix=".txt" touch.1.gz
  ```

  実行結果 []()

  ```
  // 実行前
  // touchコマンドのマニュアルページのみが存在することを確認
  user@localhost:~/man-recode$ ls
  touch.1.gz

  // 実行後
  // touch.1.txt が存在することを確認
  user@localhost:~/man-recode$ ls
  touch.1.gz  touch.1.txt
  ```
