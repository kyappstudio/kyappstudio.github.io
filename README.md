# kyappstudio.github.io

這個 repo 存在的唯一理由是 **Android App Links 的 `assetlinks.json` 必須放在
網域根目錄**。

Android 驗證連結時一律去抓 `https://<網域>/.well-known/assetlinks.json`，
**跟連結本身的路徑無關**。LiveLED 的連結長這樣：

    https://kyappstudio.github.io/LiveLEDPublic/s/#<設定碼>

很容易以為檔案該放在 `/LiveLEDPublic/.well-known/`，但那個位置 Android 從來
不會去看。放在那裡的結果是 Play Console 報「Digital Asset Links JSON 檔案未通過
檢查」外加「內容類型不是 application/json」——後者其實是 404 頁面回傳 text/html
造成的假象，兩個錯誤是同一件事。

`LiveLEDPublic` 是 GitHub Pages 的**專案網站**，只能掛在子路徑；網域根目錄屬於
**使用者網站**，而使用者網站的 repo 名稱必須剛好等於 `<帳號>.github.io`。

## 內容

    .well-known/assetlinks.json   ← 唯一重要的檔案
    .nojekyll                     ← 沒有這個，Jekyll 會忽略以點開頭的目錄
    index.html                    ← 根網址總得有東西

## 指紋

`assetlinks.json` 裡要放**兩組** SHA-256：

- **上傳金鑰**：本機 `./gradlew assembleRelease` 出來的 APK 用的
- **Play 應用程式簽署金鑰**：使用者從 Play 安裝的版本用的（Google 重新簽的）

只放前者的話，本機裝的能開，從 Play 裝的不能開——而後者才是真正的使用者。
Play 簽署金鑰的指紋在 Play Console → 設定 → 應用程式完整性 → 應用程式簽署。
