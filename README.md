<!-- v1.2.0 -> v1.3.0: 增加英文說明 (English Documentation)，支援中英雙語瀏覽 -->
# vivo X300 Ultra (V2562) 相機應用程式備份 / Camera App Backup

本儲存庫記錄與備份 vivo X300 Ultra 原廠相機相關應用程式與演算法組件。  
This repository preserves and backs up original stock camera applications and imaging algorithm components for the vivo X300 Ultra.

> [!NOTE]
> **繁體中文** | [English](#english-documentation)

---

## 繁體中文說明

> **提示**：由於主相機 APK 體積超過 400MB，超過 GitHub 單檔案大小上限，所有 APK 安裝檔案均託管於本專案的 [GitHub Releases 頁面](https://github.com/jackoxtw/vivo_x300u_camera_app/releases) 提供下載。

### 版本結構

```text
vivo_x300u_camera_backup/
├── README.md                                        # 專案說明文件
└── v16.1.1.171/                                     # 當前版本說明
```

### 備份版本列表

#### 📷 [v16.1.1.171 - 下載頁面](https://github.com/jackoxtw/vivo_x300u_camera_app/releases/tag/v16.1.1.171)
* **適用設備**：vivo X300 Ultra (V2562)
* **核心相機版本**：`16.1.1.171` (versionCode: 160101171)
* **包含組件**：
  1. `com.android.camera_v16.1.1.171.apk`（核心相機 App，約 424MB）
  2. `com.vivo.alphacamera_v9.0.apk`（影像算法服務，約 4MB）
  3. `com.android.cameraextensions_v16.apk`（系統相機擴展服務，約 64KB）
  4. `com.accordion.pro.camera_v4.2.1.zip`（蔡司專業相機組件 Split APKs，約 160MB）

### 還原 / 安裝方式

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

---

<a name="english-documentation"></a>
## English Documentation

> **Note**: Because the core camera APK is larger than 400MB (exceeding GitHub's single file limit of 100MB), all APK assets are hosted on the [GitHub Releases page](https://github.com/jackoxtw/vivo_x300u_camera_app/releases).

### Repository Structure

```text
vivo_x300u_camera_backup/
├── README.md                                        # Project documentation
└── v16.1.1.171/                                     # Version directory
```

### Archived Versions

#### 📷 [v16.1.1.171 - Release Download](https://github.com/jackoxtw/vivo_x300u_camera_app/releases/tag/v16.1.1.171)
* **Target Device**: vivo X300 Ultra (Model: V2562)
* **Core Camera Version**: `16.1.1.171` (versionCode: 160101171)
* **Included Components**:
  1. `com.android.camera_v16.1.1.171.apk` (Core stock camera app, ~424 MB)
  2. `com.vivo.alphacamera_v9.0.apk` (Imaging algorithm service, ~4.0 MB)
  3. `com.android.cameraextensions_v16.apk` (Camera extension service, ~64 KB)
  4. `com.accordion.pro.camera_v4.2.1.zip` (ZEISS Pro camera split APKs, ~160 MB)

### Restoration & Installation Guide

Download the files from the [Releases page](https://github.com/jackoxtw/vivo_x300u_camera_app/releases/tag/v16.1.1.171) and install them via ADB:

```bash
# 1. Install or downgrade the core camera app
adb install -r -d com.android.camera_v16.1.1.171.apk

# 2. Install auxiliary camera services
adb install -r -d com.vivo.alphacamera_v9.0.apk
adb install -r -d com.android.cameraextensions_v16.apk

# 3. Install ZEISS Pro camera components (extract zip first)
unzip com.accordion.pro.camera_v4.2.1.zip
adb install-multiple -r -d com.accordion.pro.camera_v4.2.1/*.apk
```
