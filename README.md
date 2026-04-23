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

| Add-on | 描述 | 連接埠 |
|--------|------|--------|
| **FRP Client** | 透過 FRP 將 Home Assistant 暴露到外網 | - |
| **Filebrowser** | 網頁版檔案管理器 | 8080 |
| **MQTT Broker** | Mosquitto MQTT Broker | 1883 / 9001 / 8883 |
| **Zigbee2MQTT** | Zigbee 閘道橋接器，取代專屬 Zigbee Hub | 8080 |
| **Node-RED** | 視覺化自動化流程編輯器 | 1880 |
| **Tailscale** | 零設定 VPN，安全組網 | - |
| **ESPHome** | ESP8266/ESP32 韌體開發工具 | 6052 |

## 開發

每個 add-on 都是獨立的資料夾，內含：
- `config.yaml` — Add-on 設定
- `Dockerfile` — 容器映像檔定義
- `build.yaml` — 建構設定
- `rootfs/` — 執行時檔案

---

Maintained by [Calvin](https://github.com/calvinastroboy)
