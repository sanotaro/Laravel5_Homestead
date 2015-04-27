http://laravel.com/docs/5.0/homestead
homested の公式ページを見てinstall する場合
bash init.sh　とコマンドを実行する必要があるが
init.sh 内に以下の記述があるが

mkdir -P ~/.homestead

windows 環境では　winows のmkdir コマンドが実行される為、必要なファイルが作成されない。
-P オプションが存在しないのでとまる。
[C:sano]
$ which mkdir
aliased as C:\Windows\System32\cmd.exe /c mkdir
C:\opt\MinGW\msys\1.0\bin\mkdir.exe

他に、~/$HOME　等の場所が C:\opt\MinGW\msys\1.0\home\sano となるので
.homestead\Homestead.yaml　の内容を修正する必要がある
Homestead.yaml の 以下の表記が　上手くいっているけど意味が今いちわかってない。
authorize: .homestead/ssh/homested_id_rsa.pub
keys:
    - .homestead/ssh/homested_id_rsa


## Laravel の　plane プロジェクトのインストール
set COMPOSER_PROCESS_TIMEOUT=5000
Had the same issue. Delete the vendor/compiled.php and run composer
$ composer update --prefer-dist
