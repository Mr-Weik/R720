# R720引导----Oc0.7.5

#### 简介

1. 此引导为联想拯救者R720，Cpu为i5-7300hq,独显1050ti(不能驱动)的引导EFI，Oc版本为0.7.5，目前可驱动版本为11.6(20G165)，后续版本未尝试，不定期会升级Oc版本
2. 因引导为Oc引导，可能具有一定的定制性，不能同clover似的通用，所以请大家使用前先具体的了解一下Oc的整体结构，可以参考小兵的精讲OpenCore  https://blog.daliansky.net/OpenCore-BootLoader.html 
3. 本机已替换网卡为Dw1820A：
   + wifi、蓝牙、隔空、随航、接力均正常使用
   + 非本网卡需要注意以下几点
     + wifi驱动
       + 移除在 `kext` 下的` AirportBrcmFixup.kext ` 的驱动
       + 移除在 `config.plist'` 下 `kernel` 中的 `AirportBrcmFixup.kext` 驱动补丁
     + 蓝牙驱动：
       + 移除在 `kext` 下的`BrcmBluetoothInjector.kext`, `BrcmFirmwareData.kext` , `BrcmPatchRAM3.kext` 的驱动
       + 移除在 `config.plist'` 下 `kernel` 中的 `BrcmBluetoothInjector.kext`, `BrcmFirmwareData.kext` , `BrcmPatchRAM3.kext` 驱动补丁
4. 补充三码：
   1. 在`config.plist` 下的 `PlatformInfo` -- `Generic` ：
      + 注入 `MLB` ,  `ROM`  , `SystemSerialNumber` , `SystemUUID`
      + 可以从 `Hackintool`下的序列号生成器获取，在苹果官网查看序列号是否有人使用（使用未查询到的序列号）
