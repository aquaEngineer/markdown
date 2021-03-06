## PHPのコーディング規約
### PSRとは
* iPSRとは、PHP-FIG（PHP Framework Interop Group）が定めた規約
* PHPには、様々なフレームワークやライブラリがありますが、それぞれコーディング規約が微妙に異なっています。   
 そこで、各フレームワークの関係者が集まったグループPHP-FIGが、PHP共通でえるようなコーディング規約を決めたのがPSRです。
* PSRにはPSR-0,PSR-1,PSR-2,PSR-4などの規約があります。   
PSR-0とPSR-4はPHPのオートローダーのためのコーディング規約、PSR-1とPSR-2は標準コーディング規約になっています。 PSR-2はPHPの最もスタンダードなコーディング規約となりつつあります。

### PSR-1
* クラス名 はUpperCamelCaseのような アッパーキャメルケース で定義しなければなりません。
* クラス定数 は UPPER_SNAKE_CASE のような アッパースネークケース で定義しなければなりません。
* メソッド名 はcamelCaseのような キャメルケース で定義しなければなりません。

### PSR-2
#### ファイル
* すべてのPHPファイルはUnix LF（改行）行末を使用する。
* すべてのPHPファイルは空白行で終わらせる。
* PHPのみのファイルの場合、終了タグ?>は省略する。

#### 空白
* 空白ではない行の末尾に空白を連続して入力しない。
* 可読性を向上させる為、関連するコードブロックを示す為に空白行を追加する事はOK

### インデント
* インデントはタブではなく、4つのスペースを使用する。
* スペースをタブと混合しないで空白のみを使用すれば、差分、パッチ、履歴、注釈の問題を回避できる。    
* 調整の為に細かいサブインデントを挿入するのも簡単になる。

### メソッド
* すべてのメソッドで可視性を宣言する。
* メソッド名には、暗黙のprivateを示すような接頭辞アンダースコアは付けない。
* メソッド名の後ろにはスペースを入れない。
* 開始/終了波括弧は単体それのみで１行に記述する。
* 開始括弧の後ろにはスペースを入れない。
* 閉じ括弧の前にはスペースを入れない。
* 引数を記述する際には、カンマの前にスペースは入れない。
* カンマの後にスペースを1つ入れる。
* デフォルト値を持つメソッド引数は最後に置く。
* 引数リストは複数の行に分割OK。その場合は1つめから改行し、1行に1つの引数を記述する。   
また、その場合、閉じ括弧と開始波括弧は1つのスペースを挟んで1行に記述する

### 比較
* 比較は可能な限り厳密な比較（===, !==）を利用するべきとしています。

### 制御構文
* (の前に1スペースを入れます。
* (の後にスペースは入れません。
* )の前にスペースは入れません。
* )の後には1スペースを入れます。

