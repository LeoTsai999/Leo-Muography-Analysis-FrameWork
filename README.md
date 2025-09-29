# Leo-Muography-Analysis-FrameWork

## ScintillatorClass
此檔案包含一Class用以建立閃爍體物件。利用此Class建立的閃爍體物件，僅能從GeneralID建立。此類別包含五種方法：
- GetID():  
  回傳此閃爍體的GenID
- GetInfo():         
    以tuple回傳此閃爍體的(GenID, 中心x座標, 中心y座標, 中心ｚ座標, LayerID)
- GetCenter():         
    以tuple回傳此閃爍體的(中心x座標, 中心y座標, 中心ｚ座標)
- GetVertices():       
    ndarray回傳此閃爍體的八個頂點。資料形狀為8*3的二維陣列

- line_cross_it_or_not(self, line_start, line_vec):    
    此方法需給予一點一方向向量決定一空間中的直線，判斷該直線是否穿過閃爍體。回傳值為一布林。line_start和line_vec都應該為tuple (x_0, y_0, z_0)和 (px, py, pz)


## 001_IDtoCoordinate
此檔案為整個工作流的第一步。設定好閃爍體長寬、閃爍體高度、每個頻道的間隔後，產出coordinates.csv檔案。此檔案為GeneralID和中心座標的對照表。此對照表由GenID 0 依序到GenID 255 (扣掉欄位名稱那行不算,第一行是GenID 0, 第二行是GenID 1, 以此類推到GenID 255)
- 需設定參數：
  - size 閃爍體長寬
  - height 閃爍體高度
  - gap 各頻道間的間隔
  - L1 第一層的高度（以中心座標z來算）
  - L2 第一層的高度（以中心座標z來算）
  - L3 第一層的高度（以中心座標z來算）
  - L4 第一層的高度（以中心座標z來算）

## 002_CombinationMaker
此檔案負責進行數值模擬，計算所有可能的觸發組合。方法為在第四層閃爍體的上表面和第一層閃爍體的下表面選超多點然後逐組合連線，當成muon ray。
函式main()中可以設定xrange和yrange, 指定掃描點範圍。
函式process_point_pair(start_point, end_points, scintillators)中可設定掃描終點與起點（也就是muon ray的起點和終點）

- V1_3  
結果被儲存為configs.npy和configs.csv。其形狀為N*256的陣列，N為觸發組合數。每一個觸發組合皆由256個布林值構成，以True代表被觸發的閃爍體。例如某config的第0, 5, 10個元素為True，表示GenID 0, 5, 10 閃爍體被觸發。

- V1_4
  不再儲存configs.npy和configs.csv。取而代之儲存configs.pkl。該物件為一個pandas dataframe。內包含configID_abs和config。


## 003_FromAbsoluteToTrlativeConfigs




## 004_Calculate_Solid_Angles






## GenID座標系統, 絕對位置座標系統, 簡易座標系統之對照
- GenID座標系統自0~255將閃爍體編號。為圖中藍色字。
- 絕對位置座標系統之中心(0,0,0)是探測器幾何中心。為人類所熟悉的笛卡兒空間座標
- 簡易座標系統為圖中紅色字所示，x和y的取值為[0,8]區間中的正整數，z取值1,2,3,4。此座標系用來簡便的描述閃爍體間的差距向量。  
![GenID座標系統對照圖](/FIgs/IMG_3635.JPG)
  
