# SINoALICE 繁中伺服器 Database

這裡的資料是截至**2019/11/20**所記錄的快取資料

---

## Art Mst

值得注意的是 **Art Mst** 比較特別, 它分為兩種版本紀錄:

- [artList.json](artList.json)
- [_artList.json](_artList.json)

### 差異是甚麼?

SINoALICE 使用 `MessagePack` 作為資料壓縮手段, 而在日服原版當中所有請求均是被加密的, 而繁中服並沒有使用加密機制, 你可以直接看到明文

而在正當的獲取手段, 你的標頭會是 `Content-Type: application/msgpack`
而此時獲取出來的資料即是正常的 `artList.json`

而 `_artList.json` 則是使用錯誤的標頭使其作為普通的Html, 因而產生出來的副產物, 你可以注意到它比原本的資料還多了 `parameterText`, 似乎是作為Debug用途的數值明文
