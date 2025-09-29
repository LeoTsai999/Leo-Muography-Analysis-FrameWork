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




## 003_FromAbsoluteToTrlativeConfigs




## 004_Calculate_Solid_Angles






## GenID座標系統, 絕對位置座標系統, 簡易座標系統之對照
- GenID座標系統自0~255將閃爍體編號。為圖中藍色字。
- 絕對位置座標系統之中心(0,0,0)是探測器幾何中心。為人類所熟悉的笛卡兒空間座標
- 簡易座標系統為圖中紅色字所示，x和y的取值為[0,8]區間中的正整數，z取值1,2,3,4。此座標系用來簡便的描述閃爍體間的差距向量。
![GenID座標系統對照圖](/Figs/IMG_3635.jpg)
  
