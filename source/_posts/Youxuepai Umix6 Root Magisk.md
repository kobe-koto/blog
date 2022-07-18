---
title: '優學派Umix6 Root Magisk'
date: 2022-01-25 15:37:46
tags: 教程
---

# 爲您的優學派(僅支持MTK)刷入Magisk來達到ROOT的目的

## 原料

> 能**與設備通訊**的**計算機**
>
> 正常的優學派（只要能進入**工廠模式**，下文會講）
>
> 一條USB**數據**綫
>
> 正常的網路環境

## 步驟

1. 安裝python。

   在 [這裏](https://www.python.org/downloads/) 下載python的最新版本。

   ![image-20220125160408833](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125160408833.png)

   若是無法訪問，請在 [這裏](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/python-3.10.2-amd64.exe) 下載python的Windows x64 3.10.2版本。

2. 安裝python，一路Next即可，這裏不在贅述。

3. 下載MTK-Client

   [MTK-Client Release](https://github.com/bkerler/mtkclient/releases)

   下載最新Release版本![image-20220125154736463](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125154736463.png)

   若是無法打開連結可訪問 [這裏](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/mtkclient-1.52.zip) 來下載1.52版本

4. 解壓您所下載的檔案

   ![image-20220125155154430](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125155154430.png)

   打開解壓文件夾，直至看到下圖所示目錄結構

   ![image-20220125155318196](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125155318196.png)

5. 複製地址欄中的地址

   ![image-20220125155417872](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125155417872.png)

6. 打開cmd

   按下 Ctrl+Shift+Esc 打開任務管理員，在檔案裏選擇"執行新工作"。

   ![image-20220125155627167](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125155627167.png)

   在"開啓(O)："欄中輸入cmd，并將"以系統管理權限建立此工作。"打勾，最後按下確定。

   ![image-20220125155854023](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125155854023.png)

   鍵入"cd /d "和你剛剛複製的目錄路徑，如圖。

   ![image-20220125160046220](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125160046220.png)

   鍵入"pip3 install -r requirements.txt"並回車。

   鍵入"python setup.py install"並回車。

7. 下載UsbDk

   在 [這裏](https://github.com/daynix/UsbDk/releases/) 下載最新的UsbDk MSI檔

   ![image-20220125161700857](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125161700857.png)

   若是聯結無法打開，請在 [這裏(x86)](‪https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/UsbDk_1.0.22_x86.msi) [這裏(x64)](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/UsbDk_1.0.22_x64_2.msi) 下載。
   
   安裝過程不再贅述，一路Next即可。
   
8. 配置adb，網上教程很多，這裏不在贅述。

9. 連結您的優學派到計算機上

   將您的優學派關機

10. 在剛剛的 cmd 窗口中鍵入"python mtk xflash seccfg unlock"並回車

    ![image-20220125164028458](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125164028458.png)

11. 按住您優學派上的所有硬體案件或只按住音量+和音量-以進入brom模式。

    在程式輸出"Port - Device detected :)"之後，您便可以鬆開您的手了。![image-20220125164403560](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125164403560.png)

    完成之後，執行"python mtk reset"來重啓您的設備。

12. 如果不成功，請依序執行以下命令：

    `

    ```bash
    python mtk e metadata,userdata,md_udc
    ```

    ```bash
    python mtk da seccfg unlock
    ```

    ```bash
    python mtk reset
    ```

    `

13. 下載您設備的全量刷機包(在優學派上被稱之爲"程序修復包")，並解壓其中的"boot.img"

    將boot.img拷貝到您的設備上(請務必牢記路徑，建議存放到"Download"文件夾中)。

14. 下載Magisk

    在 [這裏](https://github.com/topjohnwu/Magisk/releases) 下載Magisk。(若是連結無法打開，可以在 [這裏](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/Magisk-v23.0.apk) 下載)

    ![image-20220125165139354](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125165139354.png)

    並在您的設備上安裝Magisk應用程式客戶端。

15. 使用Magisk修補您的boot.img

    ![image-20220125165711807](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125165711807.png)

    ![image-20220125165753018](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125165753018.png)

    ![image-20220125165808519](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125165808519.png)

    ![image-20220125165833055](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125165833055.png)

    ![image-20220125165854668](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125165854668.png)

    將圖中紫色劃綫路徑的鏡像拷貝到電腦上。（名字不同、路徑不同，請根據設備所示尋找。）

16. 將您的設備重啓到工廠模式（上文有講）。

    執行adb reboot bootloader

    成功的話屏幕有一行小字"FASTBOOT MODE"

17. 執行"fastboot flash boot <你的patched-boot.img>"

    出現

    ```bash
    Sending ‘boot’ (131072 KB) OKAY [ 3.123s]
    Writing ‘boot’ OKAY [ 0.397s]
    Finished. Total time: 4.645s
    ```

    或類似的字樣，則為刷入成功。

    鍵入"fastboot reboot"來重啓設備。

18. 如果設備無法開機，這本教程對您的設備無用，請再次返回到 第19步 並執行"fastboot flash boot <您的原始boot.img>"

19. 如果成功開機，打開Magisk查看是否已root

    ![image-20220125171059859](https://file.koto.cc/api/raw/?path=/blog/優學派Umix6%20Root%20Magisk/image-20220125171059859.png)

教程結束！

愛怎麽折騰怎麽折騰吧（霧）

出事了我不負責
