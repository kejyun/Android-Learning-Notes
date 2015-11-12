# HAX is not installed

## 環境

> OSX Yosemite 10.10.1

> Android Studio 1.1.0

> 日期：2015-03-03

## 描述

在安裝完 Android Studio 後，跑最原始專案到 Android 模擬器時，結果居然出現 `HAX is not installed` 這個訊息

```
Starting emulator for AVD 'X86'
emulator: ERROR: x86 emulation currently requires hardware acceleration!
Please ensure Intel HAXM is properly installed and usable.
CPU acceleration status: HAX is not installed on this machine (/dev/HAX is missing).
```

原因是在安裝完 Android Studio 後，他會幫我們下載 HAX 套件，但是卻沒有幫我們安裝好 HAX

> 在選單列 Tools / Android / SDK Manager 中，在最下方可以看到他是寫 Install，可是其實是下載好未安裝的狀態

點選該套件可以在上方看到下載路徑

> /Users/kejyun/Library/Android/sdk/extras/intel/Hardware_Accelerated_Execution_Manager

在路徑中點選 `IntelHAXM_1.1.1_for_10_9_and_above.dmg` 安裝，安裝完後就可以開啟模擬器了！

> 若是 OS 版本低於 10.9，請執行 `IntelHAXM_1.1.1_for_below_10_9.dmg` 安裝 HAX

## 參考資料
* [Intel X86 emulator accelerator (HAXM installer) VT/NX not enabled](http://stackoverflow.com/questions/26521014/intel-x86-emulator-accelerator-haxm-installer-vt-nx-not-enabled)