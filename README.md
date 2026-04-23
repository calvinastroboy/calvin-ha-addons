# Calvin's Home Assistant Add-ons

Calvin 的 Home Assistant Add-on 集合倉庫。

## 安裝方式

1. 在 Home Assistant 中進入 **Settings** → **Add-ons** → **Add-on Store**
2. 點右上角 **⋮** → **Repositories**
3. 加入此倉庫 URL：
   ```
   https://github.com/calvinastroboy/calvin-ha-addons
   ```
4. 點 **Add**，新的 Add-ons 就會出現在商店列表中

## 包含的 Add-ons

| Add-on | 描述 |
|--------|------|
| **FRP Client** | 透過 FRP 將 Home Assistant 暴露到外網 |
| **Filebrowser** | 網頁版檔案管理器 |

## 開發

每個 add-on 都是獨立的資料夾，內含：
- `config.yaml` — Add-on 設定
- `Dockerfile` — 容器映像檔定義
- `build.yaml` — 建構設定
- `rootfs/` — 執行時檔案

---

Maintained by [Calvin](https://github.com/calvinastroboy)
