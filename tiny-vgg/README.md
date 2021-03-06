- 執行步驟
```
pip3 install environment.txt
```
```
unzip data.zip
```
```
python tiny-vgg.py
```
```
tensorflowjs_converter --input_format keras trained_vgg_best.h5 ./
```
詳細說明請參考 github：https://github.com/poloclub/cnn-explainer/tree/master/tiny-vgg  

- 以下講解若要自己訓練模型，要更改的內容。
  - 要先做出下兩個 excel 檔案  
    - word.xlsx：(第一行：每個類別存放圖片的資料夾名稱、第二行：那一個資料夾的類別)  
      <img width="147" alt="image" src="https://user-images.githubusercontent.com/85891503/174652497-a85cd766-8498-43a0-82c3-cbd3985b7033.png">    
    - val_annotations.xlsx  ：圖片檔名(包含驗證圖片及測試圖片)以及它們屬於的類別
      <img width="400" alt="image" src="https://user-images.githubusercontent.com/85891503/174646137-bc4978e0-a7aa-4951-a0a4-a6490108ec0e.png"><img width="150" alt="image" src="https://user-images.githubusercontent.com/85891503/174659114-a6a373a9-ac2d-4b47-b4a4-b10b1a632ec8.png"><img width="150" alt="image" src="https://user-images.githubusercontent.com/85891503/174659184-47e641b3-18ed-4251-adaf-13ca6bf127b9.png">
 
 
  - 第 250 行的 NUM_CLASS 以及 308 行的 filters 要改成自己的類別數
  - data.zip 的資料夾架構  
  ```
  data
  ├── class_2_train   
  |   ├── octopus
  │   │   └── images [octopus_train * 500]
  │   └── squid
  │       └── images [squid_train * 500] 
  ├── class_2_val
  |   ├── test_images [squid_test * 125、octopus_test * 125]
  |   └── val_images [squid_val * 125、octopus_val * 125]
  ├── word.xlsx
  └── val_annotations.xlsx 
  ```
