# kyappstudio.github.io

放 Android App Links 的驗證檔。**不要刪這個 repo。**

Android 只認 `https://kyappstudio.github.io/.well-known/assetlinks.json` 這一個
位置，刪掉的話所有 App 的連結會靜悄悄退回開瀏覽器，不會有任何錯誤訊息。

新增 App 就在那個陣列裡多加一個物件（指紋從該 App 的 Play Console 複製）。
背景與踩過的坑記在 `LiveLED/docs/SPEC.md`。

另外還有 `app-ads.txt`，AdMob 用的。**也不要刪。** AdMob 只認 Play 商店頁「開發者
網站」那個網域的根目錄，也就是 `https://kyappstudio.github.io/app-ads.txt`。
一份檔所有 App 共用：每個 App 的 Play 商店頁把網站填成 `https://kyappstudio.github.io`，
再到 AdMob 那個 App 的設定按「檢查更新」。同一個 AdMob 帳號就只有那一行，
換帳號才需要多一行。
