<!-- v1.1.0 -> v1.2.0: 增加 GitHub Releases 下載管道與說明，符合大檔案發佈規範 -->
# vivo X300 Ultra (V2562) 相機應用程式備份

本儲存庫記錄與備份 vivo X300 Ultra 原廠相機相關應用程式與演算法組件。

> **提示**：由於主相機 APK 體積超過 400MB，超過 GitHub 單檔案大小上限，所有 APK 安裝檔案均託管於本專案的 [GitHub Releases 頁面](https://github.com/jackoxtw/vivo_x300u_camera_app/releases) 提供下載。

---

## 版本結構

```text
vivo_x300u_camera_backup/
├── README.md                                        # 專案說明文件
└── v16.1.1.171/                                     # 當前版本說明
```

---

## 備份版本列表

### 📷 [v16.1.1.171 - 下載頁面](https://github.com/jackoxtw/vivo_x300u_camera_app/releases/tag/v16.1.1.171)
* **適用設備**：vivo X300 Ultra (V2562)
* **核心相機版本**：`16.1.1.171` (versionCode: 160101171)
* **包含組件**：
  1. `com.android.camera_v16.1.1.171.apk`（核心相機 App，約 424MB）
  2. `com.vivo.alphacamera_v9.0.apk`（影像算法服務，約 4MB）
  3. `com.android.cameraextensions_v16.apk`（系統相機擴展服務，約 64KB）
  4. `com.accordion.pro.camera_v4.2.1.zip`（蔡司專業相機組件 Split APKs，約 167MB）

---

## 還原 / 安裝方式

從 [Releases 頁面](https://github.com/jackoxtw/vivo_x300u_camera_app/releases/tag/v16.1.1.171) 下載對應檔案至本機後，透過 ADB 指令安裝：

```bash
# 1. 還原安裝主相機
adb install -r -d com.android.camera_v16.1.1.171.apk

# 2. 還原輔助組件
adb install -r -d com.vivo.alphacamera_v9.0.apk
adb install -r -d com.android.cameraextensions_v16.apk

# 3. 還原蔡司專業相機組件 (解壓縮後安裝)
unzip com.accordion.pro.camera_v4.2.1.zip
adb install-multiple -r -d com.accordion.pro.camera_v4.2.1/*.apk
```
