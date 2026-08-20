# kyappstudio.github.io

放 Android App Links 的驗證檔。**不要刪這個 repo。**

Android 只認 `https://kyappstudio.github.io/.well-known/assetlinks.json` 這一個
位置，刪掉的話所有 App 的連結會靜悄悄退回開瀏覽器，不會有任何錯誤訊息。

新增 App 就在那個陣列裡多加一個物件（指紋從該 App 的 Play Console 複製）。
背景與踩過的坑記在 `LiveLED/docs/SPEC.md`。
