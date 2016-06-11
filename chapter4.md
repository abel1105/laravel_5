# 四、Q&A

## Q1：重新開機後如果還要讓本機端上線該怎麼做？

## A1：

1. 打開AMPPS程式Control Center，在Apache下面點Start
2. 下面兩步驟選一個執行，差別在
     第一個：網站是不是架設在根目錄，過於複雜的專案不適合
     第二個：網站架設在根目錄，在寫 a href 值時，連結不會落落長
3. 第一種方法：依據 AMPPS 來架設 Larval 網站
    1. 進入 [_http://localhost/Test_Laravel/public/_](http://localhost/Test_Laravel/public/) 
4. 第二種方法：依據 php Artisan Serve 來架設 Laravel 網站
     分別輸入下面指令，或直接下載指令包https://goo.gl/iw1kqS
    **Test_Laravel可以取代成任一個你的資料夾名稱
     指令包也可以透過右鍵由任一個程式編輯器打開取代裡面所有的Test_Laravel**
    1. 指令：
        cd /Applications/Ampps/www/Test_Laravel
    2. 指令：
        export PATH="$AMPPS_PHP:$PATH"
    3. 指令：
        php artisan serve
    4. 進入 _http://localhost:8000/_

## Q2：AMPPS 預設 mysql 帳號/密碼是？

## A2：

1. 帳號：root 
2. 密碼：mysql
3. 如果要變更預設root的密碼的話，要先打開Apache
     再到下面連結：[_http://localhost/ampps/index.php?act=mysqlsettings_](http://localhost/ampps/index.php?act=mysqlsettings)
4. 如果要新增使用者，建議使用另外一款Sequel Pro程式
    [_http://www.sequelpro.com/_](http://www.sequelpro.com/)

## Q3：如何自動產生.env檔中的APP_KEY

## A3：

1. 開啟終端機或iterm
2. 輸入：
    `cd /Applications/AMPPS/www/資料夾名稱`
3. 指令：
    `export PATH="$AMPPS_PHP:$PATH"`
4. 輸入：
    `php artisan key:generate`
5. 再回去.env檔看就會發現已經有APP_KEY囉

## Q4：錯誤Can’t connect to local MySQL

![圖ㄧ](/image/chapter4/1.png)
## A4：

1. 如果看到上面之錯誤，代表沒有開啟AMPPS的MYSQL。
2. 如果沒開MYSQL，打開AMPPS再MYSQL下面點Start，再刷新一次頁面就可以了。
3. 如果Start按鈕按下去沒反應，代表可能你已經有別的非Apache的Mysql在運行，這時候建議你到《參、資料庫Mysql設定》照著步驟走，排除掉其他Mysql
    
4. ![圖二](/image/chapter4/2.png)

## Q5：更換phpstorm預設顏色

## A5：

1. 下載取得 icls 檔：https://github.com/kevinhowbrook/php-storm-colors
2. 直接下載zip
3. 打開 Finder 到 前往的標籤選 前往檔案夾
    1. ![圖三](/image/chapter4/3.png)
4. 複製：~/Library/Preferences/
    貼到跳出的視窗中，接著按前往
    1. ![圖四](/image/chapter4/4.png)
5. 找一下有個資料夾叫 WebIde100，或是 WebIdeXXX 看你的版本決定
    1. ![圖五](/image/chapter4/5.png)
6. 進去後新增一個資料夾叫 colors
    1. ![圖六](/image/chapter4/6.png)
7. 再點進去colors 資料夾 複製你剛剛下載的 icls 檔案
    1. ![圖七](/image/chapter4/7.png)
8. 重新開啟 phpstorm
9. 在鍵盤上同時敲 command + , (逗點)
10. 然後在旁邊的樹狀圖選 Editor → Colors & Fonts 再旁邊schema選妳剛剛複製的檔案名稱即可。
    1. ![圖八](/image/chapter4/8.png)

## Q6：Artisan Migrate 錯誤

![圖九](/image/chapter4/9.png)
## A6：

1. 先執行`composer dump-autoload`
2. 再接著執行原先預執行的artisan命令即可


