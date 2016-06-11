# 貳、安裝 github 已經現有的 Laravel 專案

## 一、設定環境、運用github

* 首先先完成《壹、安裝空白Laravel  第一步驟～第八步驟》
* 設定完成後，看你是用Source Tree 還是 Github 原生程式，都行
* 下面以Source Tree 操作為範例

## 二、Clone 專案

1. 按 +New Repository 按鈕，選Clone from URL
    1. ![圖一](/image/chapter2/1.png)
2. 到github連結複製github link 如下，記得是選HTTPS
    1. ![圖二](/image/chapter2/2.png)
3. 貼到Source URL，下面表單會自動填完，記得先不要按Clone
    1. ![圖三](/image/chapter2/3.png)
4. 先複製下面的Name
    1. ![圖四](/image/chapter2/4.png)
5. 按Destination Path 旁邊的 瀏覽 Icon
    1. ![圖五](/image/chapter2/5.png)
6. 接著先進入 應用程式 再選 AMPPS 進去
    1. ![圖六](/image/chapter2/6.png)
7. 點一下www資料夾，再按最右下角的open（記得不要進去www）
    1. ![圖七](/image/chapter2/7.png)
8. 這時候會變成這樣
    1. ![圖八](/image/chapter2/8.png)
9. 還記得你剛剛複製的嗎？在www後面加一個斜線後再貼上，下面的name就會自己產出。可以放心按Clone惹
    1. ![圖九](/image/chapter2/9.png)


## 三、安裝Laravel必備套件

1. 打開終端機或iterm，或任一可輸入指令的app都可以。
     這裡資料夾名稱自己取代為剛剛複製的文字
2. 接著輸入：
    `cd /Applications/AMPPS/www/資料夾名稱`
3. 再輸入：
    `composer install`
    如果跳出
    `command not found: composer`
    代表你還沒安裝composer，請到 《壹、安裝空白Laravel 步驟九》完成該步驟即可回來繼續執行
4. 如果成功的話，會開始自動安裝一些Laravel必要套件，要等一段時間直到最後出現
    `Compiling common classes`
    才表示安裝完成

## 四、打開程式編輯器

1. 打開你習慣的程式編輯器，指向到
    /Applications/AMPPS/www/資料夾名稱
2. 這邊以PhpStorm為例，他是一個專門用來輔助寫php語言的程式。
     下載link：
    [_https://www.jetbrains.com/phpstorm/download/_](https://www.jetbrains.com/phpstorm/download/)
     記得如果安裝後，點開提示沒有java時，記得要到下面連結下載最新osx java
    [_https://support.apple.com/kb/DL1572?locale=zh_TW_](https://support.apple.com/kb/DL1572?locale=zh_TW)

## 五、尋找環境檔

1. 打開程式編輯器後，在根目錄找一隻叫 .env 的檔案
2. 如果怎麼找就是沒發現，也不用擔心，因為在.gitignore檔案中已經預設將 .env 檔案排出在上傳github的檔案裡了，原因是怕有心人士獲得你的資料庫密碼或其他重要資料
3. 這時候你去詢問開發者就可以拿到正確的 .env 檔，亦或是自己新增一個新檔案

![圖十](/image/chapter2/10.png)
## 六、介紹環境檔

1. 這裡以新增作為介紹，首先對根目錄按右鍵，選New後再選擇File，即會跳出命名視窗
2. 在視窗中填.env等字如下圖，後按okay，即會產生相對應文件
3. 複製下面的Code貼到新增的.env檔
    1. 
    2. APP_ENV=local
         APP_DEBUG=true
         APP_KEY=SomeRandomString
        
         DB_HOST=127.0.0.1
         DB_DATABASE=homestead
        DB_USERNAME=homestead
         DB_PASSWORD=secret
        
         CACHE_DRIVER=file
         SESSION_DRIVER=file
         QUEUE_DRIVER=sync
        
         MAIL_DRIVER=smtp
         MAIL_HOST=mailtrap.io
         MAIL_PORT=2525
         MAIL_USERNAME=null
         MAIL_PASSWORD=null
         MAIL_ENCRYPTION=null
4. 從上到下介紹
    1. APP_ENV： 運行環境 - 本機端
    2. APP_DEBUG： Debug狀態 - 開啟Debug
    3. APP_KEY： 應用程式代號 - 產生方法請查閱《伍Q3》
    4. DB_HOST：資料庫網址 - 如果你是在本機架設資料庫，就維持127.0.0.1
    5. DB_DATABASE：資料庫名稱 - 請對應自己創建的資料庫
    6. DB_USERNAME： 資料庫使用者 - 請對應自己創建的資料庫使用者
    7. DB_PASSWORD： 資料庫使用者密碼 - 請對應自己創建的資料庫使用者密碼
    8. 其他維持即可

```
※詳細資料庫設定請參照《參、資料庫 Mysql 設定》
```

## 七、最後步驟

```
※下面兩步驟選一個執行即可，建議使用第2步驟
```

1. 依據 AMPPS 來架設 Larval 網站
    1. 進入 [_http://localhost/資料夾名稱/public/_](http://localhost/Test_Laravel/public/) ，有看到頁面就代表安裝成功了！！！
2. 依據 php Artisan Serve 來架設 Laravel 網站
     分別輸入下面指令，或直接下載指令包 https://goo.gl/iw1kqS
     然後之後要架站就可以透過這個指令包，但是還是要開啟Ampps的Apache
    ※指令包需要再透過右鍵由任一個程式編輯器打開後取代裡面所有的Test_Laravel為你的資料夾名稱
    1. 指令：
        `cd /Applications/Ampps/www/資料夾`
    2. 指令：
        `export PATH="$AMPPS_PHP:$PATH"`
    3. 指令：
        `php artisan serve`
    4. 進入 _http://localhost:8000/_，有看到頁面就代表安裝成功了！！！

