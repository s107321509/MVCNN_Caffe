# MVCNN於caffe中實現    

## 資料準備
1. 下載GitHub所有的文件，點選Download Zip

2. 下載12views的昆蟲影像資料集：  
https://drive.google.com/drive/folders/1H45jjmf_fjaMX8EH3WnOovtt6-gCtP9v?usp=sharing 

3. 下載驗證資料集：     
https://drive.google.com/drive/folders/1NUsoqbb2O5V6COqvL9tjbszNXo25vcdw?usp=sharing

4. 下載pretrained model：   
- 可以從Google Drive下載ModelNet40 12個視角的資料集來訓練自己的pretrained model    
https://drive.google.com/file/d/0B4v2jR3WsindMUE3N2xiLVpyLW8/view  
- 或是使用我訓練ModelNet40的pretrained model  
https://drive.google.com/file/d/1KJhkDLFfvzhICuSdxk-uqbAvo1QDqQgZ/view?usp=sharing  

5. mvccn_12view.prototxt路徑與種類數目修改：  
- 修改mvccn_12view.prototxt中的輸入層的資料路徑  
```
'data_path': './vipModel_white_background'  
```

- 修改最後一層全連接層的種類數目  
```
num_output: 5  
```
6. 將Caffe資料夾複製到目錄裡

## 訓練
開啟終端機至目錄   
```
python trainMVCNN.py
```

## 驗證
- 修改valid.py中caffe_model的檔名  
```
caffe_model='./mvcnn_vipModel_10000.caffemodel'
```

- 修改驗證資料存放路徑  
```
image_dir = r"/home/viplab/MVCNN/MVCNN_12views/valid/valid_al" 
```

- 開啟終端機至目錄  
```
python valid.py
```
