# 三、資料庫 Mysql 設定

```
使用下列此教學時機：
已經完成單獨《壹、安裝空白Laravel》《貳、安裝 github 已經現有的 Laravel 專案》任一者

```

## 一、判定有沒有在運行Mysql

1. 首先先關掉你的AMPPS，接著打開終端機或iTerm 2
2. 輸入：
    `ps ax | grep mysql`
    會吐出一列資料，如下，用意為判斷現在是否有mysql在運行
    1. [Image: file:///-/blob/EaeAAADTHiS/JwKjTSVkb9c_DQjuRTZvvQ]
3. 上面截圖表示有三個正在運行的Mysql，每一個正在運行的程式前面會以五位數的數字表示他的程序ID，而上圖最後一個程序以grep開頭的可以自動忽略，因為是我們輸入指令後才產生的程序，如果只有grep一隻程序的話，代表你的系統目前沒有mysql在運行，跳到**步驟二之二**，如果有除了grep以外的程式，如上圖，代表有mysql在運行，則跳到**步驟二之一**。
4. ※指令說明：
    `ps ax | grep mysql -> ps ax 為抓取系統所有正在運行的程序，grep mysql 為抓出程序名稱包含mysql字樣的程序`

## 二之一、判定你是否有曾安裝過Mysql

1. 接著把裡面的字放大來看看，表示/usr/local/Cellar/下面存在一個mysql
    1. 
    2. 
        `13978 ?? S 0:00.02 /bin/sh /usr/local/Cellar/mysql56/5.6.27/bin/mysqld_safe --datadir=/usr/local/var/mysql --pid-file=/usr/local/var/mysql/Abelde-MBP.pid
         14062 ?? S 0:00.97 /usr/local/Cellar/mysql56/5.6.27/bin/mysqld --basedir=/usr/local/Cellar/mysql56/5.6.27 --datadir=/usr/local/var/mysql`
2. 如果你一開完機，熱機完後，執行 `ps ax | grep mysql `後，如果馬上就檢測到有mysql在運行，代表他會自動啟動，那建議你卸載你的mysql，要不然開發laravel時會一直抓到錯的資料庫，如果開完機過了很久都沒檢測到，那就可以安心開發了。
3. 如果一直纏著你的是Cellar資料夾下的mysql，先運行下面指令：
    `brew list | grep mysql
    `將吐回的數個，分別套用到下面的命令執行：
    `brew uninstall mysql56
    `mysql56 取代成上指令回傳回的名稱，如果吐回的資料有兩個，則要執行兩次`brew uninstall`，後面接的即是上面吐回的名稱，全部解安裝後再執行一次`which mysql`看還找不找得到mysql，顯示`mysql not found`就跳到步驟三。
    例如：吐回的是 `mysql56 mysql57`
    就輸入：
    `brew uninstall mysql56
    `brew uninstall mysql57``
4. 如果不是Cellar資料夾下的mysql，直接註記在下面，之後再來處理
5. `※指令說明：
    `brew list | grep mysql` -> ``brew list``列出所有曾經安裝過的`homebrew軟體，``grep mysql` 抓取軟體中含有mysql字樣的``````
    brew uninstall * -> 截除安裝曾經用homebrew安裝的軟體`

## 二之二、判定你是否有曾安裝過Mysql

1. 先運行下面指令：
    `brew list | grep mysql`
    如果吐回來是 mysql56 或其他包含mysql的名稱（也有可能為數個，中間會用空白鍵隔開）
    如果都沒有吐回，則直接跳到步驟三
2. 將吐回的數個，分別套用到下面的命令執行：
    `brew uninstall mysql56
    `mysql56 取代成上指令回傳回的名稱，如果吐回的資料有兩個，則要執行兩次`brew uninstall`，後面接的即是上面吐回的名稱，全部解安裝後再執行一次`which mysql`看還找不找得到mysql，顯示`mysql not found`就跳到步驟三。
    例如：吐回的是 `mysql56 mysql57`
    就輸入：
    `brew uninstall mysql56
    `brew uninstall mysql57``
3. `※指令說明：
    `brew list | grep mysql` -> ``brew list``列出所有曾經安裝過的`homebrew軟體，``grep mysql` 抓取軟體中含有mysql字樣的``````
    brew uninstall * -> 截除安裝曾經用homebrew安裝的軟體`

## 三、開啟AMPPS Mysql

1. 打開AMPPS 應用程式，在Mysql下面點Start按鈕
    1. [Image: file:///-/blob/EaeAAADTHiS/h11UlqNZfYR6eXEbxXvw-w]
2. 再次輸入指令：
    `ps ax | grep mysql`
3. ` `查看有沒有下列的程序在運行/Applications/AMPPS/mysql/bin/mysqld

## 四、開啟資料庫管理器

1. 如果沒有的話，推薦一款Sequel Pro 免費的視覺化資料庫管理器
     下載Link: [_http://www.sequelpro.com/_](http://www.sequelpro.com/)
2. 安裝完後，點開位於Launchpad 的 Sequel Pro

## 五、登入Mysql

1. 如果從未改過密碼
     登入帳號是root，密碼是mysql，如果要改密碼請參《伍 Q2》
     照著下圖輸入即可，最後輸完可以先按Add to Favorites，
     他會出現在左側我的最愛，之後進來就可以不用再輸直接按就可以了
     最後再按 Connect
2. [Image: file:///-/blob/EaeAAADTHiS/rw9PtlQMs6HEtu6BpGSYtw]

## 六、新增資料庫

1. 成功進去後，點擊最左上角的 Choose Database
     裡面如下面左圖的四個資料庫是mysql預設的，不需要動
2. 如果你現在要開一個資料庫供Laravel使用，按一下Add Database
     然後自己打一個方便你辨識的英文名稱
     然後剩下的兩個欄位照下面右圖的去選擇 最後再按Add
3. [Image: file:///-/blob/EaeAAADTHiS/9R7ULe4ur87SeZd0r6takQ]

## 七、新增資料結構

1. 如果是別人開發完的後台，資料結構肯定已經創建完，在Laravel的話已經幫你寫成code了，所以你只要輸入指令匯入資料結構就好了
2. 如果你不是Clone別人的寫好的Github Laravel，而是自己想要創建Laravel專案的話，記得要跳過第九步驟與第十步驟。

## 八、設定.env環境檔

1. 介紹.env環境檔說明及位置，請參考《貳、安裝 github 已經現有的 Laravel 專案 第五、六步驟》
2. 這時候因為我們要讓Laravel 可以正確連到AMPPS的Mysql，所以我們只要改DB開頭的設定，也就是黃色這群
3. DB_DATABASE 後面的黃色字，改成你剛剛第六步驟命名的資料庫名稱
     DB_USERNAME 後面的黃色字，改成 root
     DB_PASSWORD 後面的黃色字，改成 mysql，或是後來你換密碼後的新密碼

## 九、使用原先專案創建的資料結構

```
如果是別人開發完的後台，才要做這一個步驟喔
```

1. 確認原先專案是否有寫資料結構最快的方法
    就是打開程式編輯器，查看下面位置有沒有兩個以上的檔案
     位置：根目錄/database/migrations
2. 像下圖，就有超過兩個預設檔案，其他的就是寫專案的人創建的
    1. [Image: file:///-/blob/EaeAAADTHiS/j9eqMxOCCk8ltZxdX0x8TQ]
3. 確認有大於兩個檔案時，打開你的“終端機”或”iTerm”，輸入下列一連串指令
     指令：`cd /Applications/Ampps/www/資料夾名稱`
    指令：`export PATH="$AMPPS_PHP:$PATH"`
    指令：`php artisan migrate`
4. ※指令說明：
    `cd /Applications/Ampps/www/資料夾名稱 -> 指向到專案所在的位置
    `export PATH="$AMPPS_PHP:$PATH" -> 使用事先設定好的AMPPS的PHP位置，設定步驟於《壹、安裝空白Laravel 步驟五～七、》
    `php artisan migrate ``-> artisan預設命令之一，用途為遷移事先撰寫好的資料庫`````

## 十、匯入資料庫種子Seed

```
上面的migrate是創建資料庫架構，而Seed比較像是在資料庫架構下來新增預設內容
所以一定要在migrate後才可以使用喔！！！
```

1. 確認原先專案有沒有Seed最快的方法
    就是打開程式編~~輯器，查~~看下面位置有沒有一個以上的檔案
     位置：根目錄/database/seeds
2. 如果有除了DatabaseSeeder.php以外的檔案，代表原先專案有提供Seed，而Seed用意，即把複雜的資料庫必備關聯內容已先行設定完畢
    1. [Image: file:///-/blob/EaeAAADTHiS/UjxoB3_7gImSzA9VvrVE-A]
3. 以tnl_backend_laravel專案為例，點進去UserPermissionSeeder.php，在第60行到第66行，及設定好使用者的帳號與密碼。
    可以在62行 abel 處，改成你自己習慣的登入帳號
    同理也可以在63行 123 處，改成你自己習慣的登入密碼
    1. [Image: file:///-/blob/EaeAAADTHiS/TaCrKnTqpNM7ZkqlKknVkQ]
4. 設定好後，一樣打開你的“終端機”或”iTerm”，輸入下列一連串指令
     指令：`cd /Applications/Ampps/www/資料夾名稱`
    指令：`export PATH="$AMPPS_PHP:$PATH"`
    指令：`php artisan db:seed`

```
※指令說明：
`cd /Applications/Ampps/www/資料夾名稱 -> 指向到專案所在的位置
`export PATH="$AMPPS_PHP:$PATH" -> 使用事先設定好的AMPPS的PHP位置，設定步驟於《壹、安裝空白Laravel 步驟五～七、》
`php artisan `db:seed` ``-> artisan預設命令之一，用途為寫入事先設定好的資料庫內容`````
```

