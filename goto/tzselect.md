
[](tzselect.md)
# tzselect
本体に保存されているそれぞれの地域のタイムゾーンを調べるコマンドである。
タイムゾーンを設定する際に用いる文字列を確認することもできる。他の国の時刻を知りたいときや、どんなタイムゾーンがあるのか知りたいときに便利である。

tzselectはシェルからパラメータなしで呼び出され、地域のリストが表示される。数字で地域を選ぶと、その地域にある国と都市のリストが表示される。
Enterキーを押せば、リストを再表示できる。タイムゾーンを選ぶには、その左の数字を押す。
Ctrl-Cを押すと、いつでもスクリプトを中断できる。
tzselectは実際にはタイムゾーンを変更しない。変更するには"dpkg-reconfigure","tz-date"を用いる。

実行例 [](変更しない)

```
tzselect
```

実行結果 [](変更しない)

```
Please identify a location so that time zone rules can be set correctly.
Please select a continent, ocean, "coord", or "TZ".
 1) Africa
 2) Americas
 3) Antarctica
 4) Asia
 5) Atlantic Ocean
 6) Australia
 7) Europe
 8) Indian Ocean
 9) Pacific Ocean
10) coord - I want to use geographical coordinates.
11) TZ - I want to specify the timezone using the Posix TZ format.
    #? 4(入力)
Please select a country whose clocks agree with yours.
 1) Afghanistan              20) Iran                     39) Palestine
 2) Antarctica               21) Iraq                     40) Philippines
 3) Armenia                  22) Israel                   41) Qatar
 4) Azerbaijan               23) Japan                    42) Russia
 5) Bahrain                  24) Jordan                   43) Réunion
 6) Bangladesh               25) Kazakhstan               44) Saudi Arabia
 7) Bhutan                   26) Korea (North)            45) Seychelles
 8) Brunei                   27) Korea (South)            46) Singapore
 9) Cambodia                 28) Kuwait                   47) Sri Lanka
10) China                    29) Kyrgyzstan               48) Syria
11) Christmas Island         30) Laos                     49) Taiwan
12) Cocos (Keeling) Islands  31) Lebanon                  50) Tajikistan
13) Cyprus                   32) Macau                    51) Thailand
14) East Timor               33) Malaysia                 52) Turkmenistan
15) French S. Terr.          34) Mongolia                 53) United Arab Emirates
16) Georgia                  35) Myanmar (Burma)          54) Uzbekistan
17) Hong Kong                36) Nepal                    55) Vietnam
18) India                    37) Oman                     56) Yemen
19) Indonesia                38) Pakistan
    #? 23(入力)

The following information has been given:

        Japan

Therefore TZ='Asia/Tokyo' will be used.
Selected time is now:   Tue Jan  9 18:45:08 JST 2024.
Universal Time is now:  Tue Jan  9 09:45:08 UTC 2024.
Is the above information OK?
1) Yes
2) No
   #? 1(入力)

You can make this change permanent for yourself by appending the line
        TZ='Asia/Tokyo'; export TZ
to the file '.profile' in your home directory; then log out and log in again.

Here is that TZ value again, this time on standard output so that you
can use the /usr/bin/tzselect command in shell scripts:
Asia/Tokyo
```
### オプション一覧
    
- **-c**

  コード
    大陸、国、都市の順に入力する代わりに
    緯度経度を打ち込み、最も近い都市を含むタイムゾーンから選択する。
    COORDはISO 6709表記を使用する。
    日本なら北緯35度41分、東経139度41分であるため、「+3541+13941」であり、ブエノスアイレスならば「-35-058」or「-3436-05826」である。
    「緯度経度だけでも理解してくれる。

  実行例 [](変更しない)

  ```
  tzselect -c +35+139
  ```

  実行結果 [](変更しない)

  ```
  Please identify a location so that time zone rules can be set correctly.
  Please select one of the following timezones, echo listed roughly in increasing order of distance from +35+139.
  1) Japan                                      6) Guam, Northern Mariana Islands
  2) Russia - MSK+08 - Sakhalin Island          7) Russia - MSK+06 - Tomponsky, Ust-Maysky
  3) Russia - MSK+07 - Amur River               8) China - Beijing Time
  4) Korea (South)                              9) Russia - MSK+07 - Oymyakonsky
  5) Korea (North)                             10) Palau
     #? 1

  The following information has been given:

          coord +35+139
          Japan

  Therefore TZ='Asia/Tokyo' will be used.
  Selected time is now:   Tue Jan  9 19:00:09 JST 2024.
  Universal Time is now:  Tue Jan  9 10:00:09 UTC 2024.
  Is the above information OK?
  1) Yes
  2) No
     #? 1

  You can make this change permanent for yourself by appending the line
          TZ='Asia/Tokyo'; export TZ
  to the file '.profile' in your home directory; then log out and log in again.

  Here is that TZ value again, this time on standard output so that you
  can use the /usr/bin/tzselect command in shell scripts:
  Asia/Tokyo
  ```

- **-n**

    cを使用したとき、地域リスト表示の最大値を設定する（デフォルトは10）。

  実行例 [](変更しない)

  ```
  tzselect -c +35+139 -n 2
  ```

  実行結果 [](変更しない)

  ```
  tzselect -c +35+139 -n 2
  Please identify a location so that time zone rules can be set correctly.
  Please select one of the following timezones, echo listed roughly in increasing order of distance from +35+139.
  1) Japan
  2) Russia - MSK+08 - Sakhalin Island
  #? 1

  The following information has been given:

          coord +35+139
          Japan

  Therefore TZ='Asia/Tokyo' will be used.
  Selected time is now:   Tue Jan  9 19:01:59 JST 2024.
  Universal Time is now:  Tue Jan  9 10:01:59 UTC 2024.
  Is the above information OK?
  1) Yes
  2) No
  #? 1

  You can make this change permanent for yourself by appending the line
          TZ='Asia/Tokyo'; export TZ
  to the file '.profile' in your home directory; then log out and log in again.

  Here is that TZ value again, this time on standard output so that you
  can use the /usr/bin/tzselect command in shell scripts:
  Asia/Tokyo
  ```
